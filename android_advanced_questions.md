### Question: What is the difference between `StateFlow` and `SharedFlow`?

**Answer:**
- **`StateFlow`** is a state-holder observable flow that emits the current and new state updates to its collectors. It always has a value, requires an initial value, and only emits the last known value to new collectors. It's ideal for observing UI state in a ViewModel.
- **`SharedFlow`** is a hot flow that emits values to all collectors. It can be configured to not have an initial value and can be used to broadcast events that should be consumed only once by multiple subscribers (e.g., showing a Snackbar message).

### Question: In Jetpack Compose, when should you use `rememberSaveable` instead of `remember`?

**Answer:**
- **`remember`** is used to store an object in the composition. This object is kept in memory as long as the composable remains in the composition. However, it does **not** survive configuration changes (like screen rotation) or process death.
- **`rememberSaveable`** works like `remember` but also saves the state to a `Bundle`. This allows the state to survive configuration changes and process death, automatically restoring it when the composable is recreated. Use it for any state that should not be lost when the user rotates their device.

### Question: Explain the different launch modes for an Android Activity.

**Answer:**
There are four launch modes for an Activity:
1.  **`standard` (Default):** A new instance of the Activity is created in the task stack for every intent.
2.  **`singleTop`:** If an instance of the Activity already exists at the top of the current task stack, the system routes the intent to that instance through an `onNewIntent()` call. If not, a new instance is created.
3.  **`singleTask`:** The system creates a new task and instantiates the Activity at the root of the new task. If an instance already exists in any task, the system routes the intent to that existing instance through `onNewIntent()` and clears all activities on top of it in its stack.
4.  **`singleInstance`:** Same as `singleTask`, but the system does not launch any other activities into the task holding this instance. The Activity is always the single and only member of its task.

### Question: In Jetpack Compose, how can you prevent unnecessary recompositions for a class that is not inherently stable?

**Answer:**
You can prevent unnecessary recompositions by ensuring Compose treats your types as **stable**. A type is stable if its public properties are immutable (`val`) and all its type arguments are also stable.

If you have a class from an external library or one with a `var` property that you know won't change in a way that affects the UI, you can signal stability to the Compose compiler in two ways:
1.  **`@Immutable` Annotation:** Use this for classes where all properties are read-only (`val`) and will never change after construction. This is a stronger guarantee than `@Stable`.
2.  **`@Stable` Annotation:** Use this to promise the compiler that if any public property of the class changes, you will notify composition by calling `State.value` (e.g., via `mutableStateOf`). You are also promising that the result of the `equals()` method will always be the same for the same two instances.

By marking classes with these annotations, you help the recomposition process skip composables whose parameters haven't truly changed.

***

### Question: Explain the difference in exception handling between `coroutineScope` and `supervisorScope`.

**Answer:**
The key difference lies in how they handle failures within their child coroutines, a concept known as **structured concurrency**.

* **`coroutineScope`:** Follows a "fail-fast" or "all-or-nothing" policy. If any child coroutine within this scope fails with an exception, the scope immediately **cancels all other children** and then re-throws the exception to its own caller. It's used when the child coroutines are tightly coupled and a failure in one makes the others irrelevant.
* **`supervisorScope`:** Isolates failures. If a child coroutine fails, the `supervisorScope` **does not cancel its other children**. The exception is handled by the `CoroutineExceptionHandler` if provided. This is ideal when child coroutines are independent tasks, and the failure of one should not affect the others (e.g., multiple network calls to fetch different data for a screen).

***

### Question: In Hilt, what is the practical difference between the `@Singleton` and `@ActivityScoped` annotations?

**Answer:**
The difference is the **lifecycle and scope** of the provided dependency instance.

* **`@Singleton`:** This annotation scopes a dependency to the `ApplicationComponent`. An instance is created only once during the application's entire lifecycle. The same instance is provided every time it's requested anywhere in the app. This is suitable for objects that are expensive to create and are needed globally, like a Retrofit instance, Room database, or a user data repository.
* **`@ActivityScoped`:** This scopes a dependency to the `ActivityComponent`. The instance is created once per `Activity` instance and is shared across all fragments within that activity. It's destroyed when the `Activity` is destroyed. This is useful for dependencies that need to hold state specific to a single activity flow but needs to be shared among its fragments.

***

### Question: How would you design a robust offline-first data synchronization mechanism for a mobile app?

**Answer:**
A robust offline-first architecture ensures the app is always usable, with data being seamlessly synchronized with a remote server in the background. The key components would be:

1.  **Single Source of Truth (SSOT):** A local database (like **Room**) acts as the SSOT. The UI always reads data from and writes data to this database directly.
2.  **Repository Pattern:** A repository layer abstracts the data sources. It's responsible for fetching data from the network and saving it to the local Room database.
3.  **Network API:** A service (using **Retrofit**) to communicate with the remote backend.
4.  **Background Processing:** A reliable background job scheduler (like **WorkManager**) is crucial. It handles the synchronization logic, ensuring it runs even if the app is closed. It can be configured with constraints like network availability.
5.  **Conflict Resolution:** Implement a strategy to handle cases where data has been changed both locally and on the server. Common strategies include "last-write-wins" (using timestamps) or more complex merging logic.
6.  **Paging & Caching:** For large datasets, use the **Jetpack Paging 3** library with its `RemoteMediator` API. `RemoteMediator` is designed specifically for this use case, orchestrating network fetches and local database saves as the user scrolls.