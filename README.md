# 🧠 Android Engineer Interview Questions

![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/kotlin-%237F52FF.svg?style=for-the-badge&logo=kotlin&logoColor=white)


_Your complete companion for mastering Android, Kotlin, Jetpack Compose & System Design interviews._

Curated by [Akshay Nandwana](https://www.linkedin.com/in/anandwana001/)


## Book 1:1 Session here -> [Click Here](https://rzp.io/l/HVG4Zx4qFO)

## Complete Android Engineer Roadmap
* [Roadmap 2024 - Topics](#android-roadmap-2024)
* [Roadmap 2024 - Week Schedule](https://www.linkedin.com/pulse/android-engineer-interview-prep-map-akshay-nandwana-owkbf/?trackingId=CDzA28GvQN604AVSCv2itA%3D%3D)

## Detailed Question and Answers
[Question and Answers](https://github.com/anandwana001/android-interview/blob/main/Detail%20Questions%20and%20Answers.md)


## Interview Contents

* [Kotlin](#kotlin)
* [Android](#android)
* [Lifecycle](#lifecycle)
* [Networking](#networking)
* [Webview](#webview)
* [Dependency Injection](#dependency-injection)
* [Jetpack Compose](#jetpack-compose)
* [Thread](#thread)
* [Architecture](#architecture)
* [Design Pattern](#design-pattern)
* [System Design](#system-design)
* [Libraries](#libraries)
* [Common Question](#common-question)
* [Questions from Company](#questions-from-company)
* [Top 10 Kotlin Coroutines Interview Questions](#top-10-kotlin-coroutines-interview-questions)
* [Kotlin Sheet 2024](#kotlin-sheet-2024)
* [Jetpack Compose Sheet 2024](#jetpack-compose-sheet-2024)

## Kotlin
- **What is the difference between `const val` and `val`?**
    - Both are used to define read-only properties, but
    - `const val` properties should be initialized at compile-time whereas `val` properties can be initialized at runtime
    - If we decompile, `const val` variable will replace with its value but `val` not, because it can be initialized at runtime
    -     const val BASE_URL = "https://github.com"
          val githubHandle = "anandwana001"
          val repoName: String
- **What is so interesting about `data class`?**
   - Uses to hold data
   - Pre-functions like `toString`, `equals`, `copy`, and `componentN`
   - Data classes cannot be abstract, open, sealed, or inner.
   - Data classes cannot extend other classes
   - Supports destructuring declaration
- Is singleton thread-safe? vs Object?
- **What are the different types of scope functions?**
   - Let = `T.let { R }`
        - lambda result (R) is the return type
        - can be performed on any `T` type object
        - lambda reference is `it`
        - suitable for null check
   - Run = `T.run { R }`
        - same as `let`, but mostly used in initializing an object
        - lambda reference is `this`
        - suitable for null check
   - With = `with(T) { R }`
        - if T is nullable object use `run` else use `with(T)`
        - lambda reference is `this`
        - not suitable for null check
   - Also = `T.also { T }` 
        - when need to perform multiple operations in chain use `also`
        - lambda reference is `it`
   - Apply = `T.apply { T }`
        - when need to perform the operation on the `T` object and return the same use `apply`
        - lambda reference is `this`
        - suitable for null check
- What are the different Coroutine Scopes?
- How to manage series and parallel execution?
- Difference between Flow/SharedFlow/StateFlow and elaborate it.
- What happens if we call `.cancel()` from a coroutine scope?
- What is an Init block in Kotlin?
- How to choose between apply and with?
- What is inline function in Kotlin?
- Difference between Coroutine and Java Thread
- Why Coroutines are light weight?
- How does Coroutine switch context?
- When to use Kotlin sealed classes?
- Suspending vs Blocking in Kotlin Coroutines
- What are Dispatchers and Name all of them
- On which thread Dispatchers .Default execute the task or use which thread?
- Dispatchers .Default vs Dispatcher .IO
- What is SupervisorScope?
- Exception Handling in Coroutine
- Map vs FlatMap in kotlin
- Singleton Pattern in Kotlin with object keyword
- Collections API in Kotlin
- What is Unidirectional Flow
- StateFlow vs SharedFlow
- Builder Pattern in Kotlin
- Higher Order Functions in Kotlin
- Covariance in Kotlin
- Delay vs Thread.sleep? [Answer](https://www.linkedin.com/posts/anandwana001_coding-datastructures-jetpackcompose-activity-7192723727661350912-cpp-?utm_source=share&utm_medium=member_desktop)

## Android
 - How does Garbage collection works?
 - What is a dangling pointer?
 - Elaborate Memory Leak?
 - Explain fragment Lifecycle when it comes to ViewPager and sliding between different fragments.
 - Difference between FragmentStateAdapter and FragmentStatePagerAdapter.
 - Difference between Serializable and Parcelable? What are the disadvantages of Serializable?
 - How you could implement observable SharedPrefs or observable Databases i.e. Observe a certain key/table/query?
 - How does layout inflation work from xml tags to view references in memory?
 - What is a Thread, Handler, Looper, and Message Queue?
 - What are the different methods of concurrency on Android? Can you explain the difference between ExecutorService vs CachedThreadPool vs FixedThreadPool vs AsyncTasks vs HandlerThreads?
 - How does `ViewModel` instance provide to Activity and Fragment? How does `ViewModelProviderStore` decide when to retain the instance?
 - How do you inspect and solve the Jank issue? [here](https://developer.android.com/studio/profile/jank-detection)
 - How does the OutOfMemory happen? 
 - How do you find memory leaks in Android applications?
 - What is Doze? What about App Standby? 
 - What does `setContentView` do?
 - Process of creating a custom view
 - Deeplink understanding and architecture
 - Notifications
 - Difference between Fragment Lifecycle Observer and View Lifecycle Observer.
 - When should you use a Fragment rather than an Activity?
 - Explain the Android push notification system.
 - How LiveData is different from ObservableField?
 - What is the difference between setValue and postValue in LiveData?
 - What is process death?
 - What is ViewModelScope and How does it work internally?

  
### Lifecycle
 - How to keep a video maintain a playing state when we rotate the screen?
 - How many callbacks are in Fragments?
 - What could be the reasons why `onPause` didn't get triggered?
 - What kind of events trigger `onPause()` to run?
 - In what scenario does the "onDestory" get called directly after "onCreate"?
 - Which callback gets called on Activity when an AlertDialog is shown?
 - What's the lifecycle in PIP (Picture-in-Picture)?
 - What happens if you rotate the device?
 - Inside a viewpager (Fragment state pager adapter) what will be the lifecycle of the fragments when you swap from one tab to another?
 - Why onActivityCreated is now depreciated in Fragment?
 - Which callback should I use if I want to know when my activity came to the foreground?
 - When is onActivityResult called?
 - What does setRetainInstance do and how you can avoid it?
 - What callbacks trigger when a Dialog opens up? In both cases, the dialog is attached from the same activity/fragment and another activity/fragment.
 - What do `launchWhenCreated`, `launchWhenStarted`, and `launchWhenResumed` functions do?
 - Fragment Callbacks when moving from one fragment to another and coming back to prev one?
 - Does onCreateView get called after coming to a fragment from top fragment?
 - When does ViewModel not survive


#### Important Lifecycle Points to Remember

##### Opening a fragment from Activity

Code
```
supportFragmentManager.beginTransaction()
    .replace(R.id.fragment_container, FragmentA())
    .commit()
```

Callbacks
| | |
|--|--|
| MainActivity  |  onCreate |
| FragmentA   |    onAttach |
| FragmentA      |    onCreate |
| FragmentA    |      onCreateView |
| FragmentA    |      onViewCreated |
| FragmentA    |      CREATED == Lifecycle.State |
| FragmentA    |      onViewStateRestored |
| FragmentA    |      onStart |
| FragmentA     |     STARTED == Lifecycle.State |
| MainActivity   |    onStart |
| MainActivity   |    onResume |
| FragmentA   |       onResume |
| FragmentA    |      RESUMED == Lifecycle.State |
| MainActivity    |   onAttachedToWindow |


#### Adding a Fragment from a Fragment

Code
```
parentFragmentManager.beginTransaction()
    .add(R.id.fragment_container, FragmentB())
    .commit()
```
```
parentFragmentManager.beginTransaction()
    .add(R.id.fragment_container, FragmentB())
    .addToBackStack(null)
    .commit()
```

Callbacks
| | |
|--|--|
| FragmentB   |    onAttach |
| FragmentB   |    onCreate |
| FragmentB   |    onCreateView |
| FragmentB   |    onViewCreated |
| FragmentB   |    CREATED == Lifecycle.State |
| FragmentB   |    onViewStateRestored |
| FragmentB   |    onStart |
| FragmentB   |    STARTED == Lifecycle.State |
| FragmentB   |    onResume |
| FragmentB   |    RESUMED == Lifecycle.State |


#### Replacing a Fragment from a Fragment

Code
```
parentFragmentManager.beginTransaction()
    .replace(R.id.fragment_container, FragmentB())
    .addToBackStack(null)
    .commit()
```

Callbacks
| | |
|--|--|
| FragmentA  | onPause |
| FragmentA  | onStop |
| FragmentB  | onAttach |
| FragmentB  | onCreate |
| FragmentB  | onCreateView |
| FragmentB  | onViewCreated |
| FragmentB  | CREATED == Lifecycle.State |
| FragmentB  | onViewStateRestored |
| FragmentB  | onStart |
| FragmentB  | STARTED == Lifecycle.State |
| **FragmentA**  | **onDestroyView** |
| FragmentB  | onResume |
| FragmentB  | RESUMED == Lifecycle.State |


Code
```
parentFragmentManager.beginTransaction()
    .replace(R.id.fragment_container, FragmentB())
    .commit()
```

Callbacks
| | |
|--|--|
| FragmentA  | onPause |
| FragmentA  | onStop |
| FragmentB  | onAttach |
| FragmentB  | onCreate |
| FragmentB  | onCreateView |
| FragmentB  | onViewCreated |
| FragmentB  | CREATED == Lifecycle.State |
| FragmentB  | onViewStateRestored |
| FragmentB  | onStart |
| FragmentB  | STARTED == Lifecycle.State |
| FragmentA  | onDestroyView |
| **FragmentA**  | **onDestroy** |
| **FragmentA**  | **onDetach** |
| FragmentB  | onResume |
| FragmentB  | RESUMED == Lifecycle.State |

#### Coming Back to Previous Fragment after Adding

Note: If `addToBackStack` is not used, and back stack is empty, nothing will happen when calling `popBackStack()` function

Code
```
// FragmentA
parentFragmentManager.beginTransaction()
    .add(R.id.fragment_container, FragmentB())
    .addToBackStack(null)
    .commit()

// FragmentB
parentFragmentManager.popBackStack()
```

Callbacks
| | |
|--|--|
| FragmentB  | onPause  |
| FragmentB  | onStop |
| FragmentB  | onDestroyView |
| FragmentB  | onDestroy |
| FragmentB  | onDetach |

FragmentA is visible. No FragmentA callbacks as FragmentA is always there, neither the view nor the lifecycle get affected.

#### Coming Back to Previous Fragment after Replacing


Note: If `addToBackStack` is not used, and back stack is empty, nothing will happen when calling `popBackStack()` function

Code
```
// FragmentA
parentFragmentManager.beginTransaction()
    .replace(R.id.fragment_container, FragmentB())
    .addToBackStack(null)
    .commit()

// FragmentB
parentFragmentManager.popBackStack()
```

Callbacks
| | |
|--|--|
| FragmentB  | onPause | 
| FragmentB  | onStop | 
| **FragmentA**  | **onCreateView** | 
| **FragmentA**  | **onViewCreated** | 
| **FragmentA**  | **CREATED** == Lifecycle.State |
| **FragmentA**  | **onViewStateRestored** | 
| **FragmentA**  | **onStart** | 
| **FragmentA**  | **STARTED** == Lifecycle.State |
| FragmentB  | onDestroyView | 
| FragmentB  | onDestroy | 
| FragmentB  | onDetach | 
| **FragmentA**  | **onResume** | 
| **FragmentA**  | **RESUMED** == Lifecycle.State |

FragmentA view is created again. When replacing, the FragmentA view gets destroyed, `onDestroyView` gets called so when coming back it calls `onCreateView` to initialise the view again.
Though, `onCreate` will not get called again.

#### Lifecycle State

There are 5 States:
 - DESTROYED
 - INITIALIZED
 - CREATED
 - STARTED
 - RESUMED

![](https://developer.android.com/static/images/guide/fragments/fragment-view-lifecycle.png)


##### Points to Remember

States are based on Context/Scope you are using in. 
Example:
```
viewLifecycleOwner.lifecycleScope.launch {
    repeatOnLifecycle(Lifecycle.State.CREATED) {
        //...
    }
}
// viewLifecycleOwner => Lifecycle of the View
// should be used between onCreateView() and onDestroyView()
```

```
this.lifecycleScope.launch {
    repeatOnLifecycle(Lifecycle.State.CREATED) {
        //...
    }
}
// this => Lifecycle of Fragment or Activity
```

| | |
|--|--|
| CREATED | - listen in `onDestroyView` (if not View lifecycle) and in `onStop`, `onSavedInstance` too  |
| STARTED | - listen in `onStart`, `onPause` |
| RESUMED | - listen in `onResume` |
| DESTROYED | - listen in `onDestroyView` (if View lifecycle) and in `onDestroy` |
| CREATED | - listen in `onViewStateRestored` (if View lifecycle) |
| CREATED | - listen in `onCreate`, `onCreateView`, `onViewCreated`, `onViewStateRestored` (if not View lifecycle) |


#### Examples

- if state CREATED and app moves to background, it will listen. Hence, Avoid UI work here
- use state CREATED if need to complete action even after Fragment View destroy
- 

### Networking
- What is the role of OkHttp and Retrofit?
- What design pattern does Retrofit use?
- How would optimize the handling of access token expiration? How would you handle a retry network call when the API fails? (Custom Interceptor response)


### Webview
- What are the problems around security when dealing with `WebView`?
- How to interact or make connections with JavaScript?


### Dependency Injection
- Provides vs binds
- Subcomponent vs. component dependency, what is the difference under the hood
- What is a subcomponent and what is its use? How do you use qualifiers or how would you provide different instances of a class with the same data type? Constructor Injection V/s Method Injection? What is the scope? Singleton Annotation?
- What is Circular dependency in dagger? and how to resolve it
- What's interesting about Hilt?
- Did you use Koin? What are your thoughts on it?


### Jetpack Compose
- How to launch a coroutine from a composable function? - [LaunchedEffect](https://www.droidcon.com/2021/10/28/jetpack-compose-side-effects-ii-remembercoroutinescope/)
- How to launch a coroutine from a non-composable function, but tied to composition? - [rememberCoroutineScope()](https://www.droidcon.com/2021/10/28/jetpack-compose-side-effects-ii-remembercoroutinescope/)
- What is recomposition? [Recomposition](https://developer.android.com/jetpack/compose/mental-model#recomposition)
- **What is `remember` in compose?**
  - A composable function to remember the value produced by a calculation only at the time of composition. It will not calculate again in recomposition.
  - Recomposition will always return the value produced by composition.
  - Whole Compose is based on the concept of `Positional Memoization`
  - At the time of recomposition, `remember` internally calls a function called `rememberedValue()` whose work is to look into the `slotTable` and compare if the previous value and the new value have any difference, if not return, else update the value
- Why and when to use `remember {}`?
- Difference between `LazyColumn` and `RecyclerView`?
- What is AndroidView in compose?
- What is the lifecycle of composeables? [Lifecycle](https://developer.android.com/jetpack/compose/lifecycle)
- How to avoid recomposition of any composable, if the state is not changed? [Smart Recomposition](https://developer.android.com/jetpack/compose/lifecycle#add-info-smart-recomposition)
- What are stable types that can skip recomposition?
- What is State?
- What is MutableState and how does recomposition happen?
- How to retain State across recomposition and configuration changes?
- Difference between Stateless and Stateful composeables?
- What are your thoughts on flat hierarchy, constraint Layout in compose vs. the older view hierarchy in xml
- Difference b/w remember and LaunchedEffect
- Does re-composition of `ComposeItem1` bring any effect on `ComposeItem2`? If yes, then how? 
  - `ComposeParent() { ComposeItem1 {} ComposeItem2() {...} } `
  - What is `CompositionLocal`?
- Custom views in compose
- Canvas in Compose
- What are the benefits of Jetpack Compose?
- How does Jetpack Compose integrate with existing Android frameworks and libraries?
- What are the best practices for performance optimization in Jetpack Compose?
- How is navigation handled in Jetpack Compose?
- What is Strong Skipping Mode? [Answer](https://www.linkedin.com/posts/anandwana001_coding-datastructures-jetpackcompose-activity-7193437801365823488-SlVT?utm_source=share&utm_medium=member_desktop)
- Compare and contrast `LaunchedEffect`, `SideEffect`, and `DisposableEffect`. Provide a clear use case for each one.
  - `LaunchedEffect` is used to run a suspend function (coroutine) safely from a composable. It launches when the composable first enters the composition and cancels when it leaves. It will relaunch if its `key` parameter changes.
  Use Case is to run a one-time suspend action when the composable first enters the composition, such as fetching initial data from a network or showing a `Snackbar`
  - SideEffect is used to execute a block of code after every successful recomposition. It's an escape hatch to share Compose state with non-Compose code.
  Use Case is to publish Compose state to non-Compose code, for example, updating an analytics library with the latest state value after every recomposition.
  - DisposableEffect is used for non-suspending side effects that require an explicit cleanup (teardown) process.
  Unlike LaunchedEffect, the main effect block of DisposableEffect runs synchronously during composition. This block executes whenever the composable enters the Composition or when its given key(s) change. Its primary function is to provide a mandatory onDispose block for cleanup.
  Use Case: Its primary use case is for managing listeners or observers from the Android framework that are not Compose-aware. For instance, registering a LifecycleObserver or a BroadcastReceiver inside the effect block, and then unregistering it within the mandatory onDispose block to prevent memory leaks.


## Thread
 - Different types of threads?
 - Difference between different types of thread?
 - Thread <-> Handler <-> looper
 - UI vs Background Thread
 - How do you know when some process if blocking a UI thread?

## Architecture
 - What are SOLID principles?
 - What is MVVM?
 - Brief about Android Architecture.
 - MVP vs MVVM?
 - Is there any issue in the Presenter in the MVP?
 - Clean Architecture
 - MVVM vs MVI
 - What is Clean Architecture in MVVM
 - What are Provides and Binds in your Dagger library


## Design Pattern
 -  What is SOLID principle?
 - What are different design patterns you know about?
 - What is a creational pattern?
 - What is a structural pattern?
 - What is a behavioral pattern?
 - Create Singleton Pattern without Kotlin default implementation
 - Create Observer Pattern
 - Create Adapter Pattern
 - How to make a Singleton Pattern Thread Safe?
 - What is Dependency Inversion
 - Write a real-life example of Dependency Injection without using any library
 - Explain how Android Architecture components (ViewModel, LiveData, etc.) utilize design patterns behind the scenes

## System Design
 - Design Image Loading Library
 - Design Image Downloading Library
 - Design LRU Cache
 - Design a real-time Twitter feed timeline. How will you structure the backend? Will you use WebSocket or REST for this use case? Justify. 
 - Design Networking Library
 - Design Checkout Screen
 - Design Error handling Structure
 - REST <-> Web Sockets
 - Implement caching mechanism
 - Build an offline-first app
 - Design Analytics Library


## Libraries
 - How does Glide internally work?
 - How does retrofit work internally?
 - ViewModel internal working
 - How will you choose between Dagger 2 and Dagger-Hilt?

## Common Question
 - `String` vs `StringBuilder`
 - `==` vs `.equals`?
 - `===` vs `==`?
 - Java OOP concepts
 

## Questions from Company
| Company | Questions |
|  --- | --- |
| Booking.com | <ul><li>Implement findViewById method</li> <li>Given a list of words as input, output another list of strings, each containing words that are mutual anagrams</li> <li>Identify whether four sides (given by four integers) can form a square, a rectangle or neither</li> <li>Output a delta encoding for the sequence. In a delta encoding, the first element is reproduced as-is. Each subsequent element is represented as the numeric difference from the element before it</li> <li>Three integer arrays are given with duplicate numbers. Find the common elements among three arrays</li> <li>Twisted question related to ConcurrentModificationException in an ArrayList</li> <li>How do you implement a hotel list and detail screen? Discuss what all APIs You will create and how the layout will be </li> <li>Fragments & their lifecycle, Activity lifecycle, Views, Layouts </li> <li> Background task in Android - Asynctask, service, intent services, etc </li> <li> Given dates and number of check-in and check-out on those dates. Find the busiest day in the hotel. [Merge Array interval type question]</li> <li> Given an array, determine if there are repeated elements. If an element is repeated more than 3 times, return those elements. This question is basically doing a hash and checking if the hash already exists. Someone used a Map and a Set. </li> <li> Given a list of positive words, negative words, and a review, determine if the review is flagged as positive, negative, or neutral. Someone solved it using a Set. Someone just needed to do some count (+ or -) regarding where the word appeared (positive list or negative). </li> </ul>| 
| Spotify | <ul> <li> Design components and overall architecture for a Search feature in an Android application. [Spotify - Android Engineer II - London, UK - Sep 2022] </li> <li> Design a Disk based Cache for the client. [Spotify System Design Android/iOS Client] `Platform independent, Key will be 32 bytes, Value can be anything but in Byte array, Cache should be persistent, Cache should max hold 100k+ Objects, Cache Max size should be configurable ( Max Size: 10 MB upto 1GB), Cache should be opaque, Cache should be Secure` </li> <li>[Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/) </li> <li> [Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/) </li></ul>|
| PhonePe | <ul> <li> Minimum Meetroom scheduling </li> <li> Anagram Strings based question </li></ul> |
| Paytm | <ul> <li> To check if strings are rotations of each other or not. If they are in rotation print the no. of rotations. </li> <li> Find the string is anagram or not </li> <li>Design components and overall architecture for a Search feature in an Android application</li> <li> Sort an array of 0s, 1s and 2s </li> <li> Abstract vs Interface </li> <li> Android Memory related </li></ul> |
| Meesho | <ul> <li> SOLID principles </li> <li> Dagger, why use dependency injection, what if we do not think it is important, like alternatives? How to create our own dependency injection library. </li> <li> why use MVVM over MVP, think outside the box, we could have used observables using RxJava, etc. - open-ended questions around it </li> <li> Multi-Module benefits and why use it</li> <li> How to handle dependencies or abstraction in multi-module </li> <li> val vs const </li> <li> inline keyword </li> <li> lateinit vs lazy </li> </ul>|


------

## Android Roadmap 2024
| Topics | Sub-Topics |
|  --- | --- |
| Programming Languages | <li>Kotlin</li><li>Java</li> |
| Android Architecture | ![image](https://developer.android.com/static/guide/platform/images/android-stack_2x.png) |
| Runtime | <li>Dalvik Virtual Machine</li><li>Android Runtime</li> |
| Android Manifest | <li>Package</li><li>Application Id</li> |
| Permissions | <li>Install-time Permissions</li> <li>Special Permissions</li> <li>Runtime Permissions</li><li>Permissions Groups</li>|
| Android Build | <li>APK</li><li>AAB</li> |
|Thread|<li>Processes</li><li>Threads</li><li>Inter Process Communication</li><li>Handlers</li><li>Loopers</li><li>Message Queue</li><li>UI Thread</li><li>Background Thread</li><li>Heap & Stack</li>|
| Fundamental Components | <li>Activity</li><li>Services</li><li>Broadcast Receiver</li><li>Content Provider</li>|
| Intent |<li>Implicit Intent</li><li>Explicit Intent</li><li>Intent Filters</li><li>Intent Flags</li>|
|Activity|<li>Activity Lifecycle</li><li>Tasks and Back Stacks</li><li>Bundles</li><li>Parcelables</li><li>Recent Screens</li><li>App Shortcuts</li><li>Context</li>|
|Services|<li>Service Lifecycle</li><li>Foreground Service</li><li>Background Service</li><li>Bound Service</li><li>AIDL</li><li>Job Scheduler</li><li>WorkManager</li><li>IntentService</li>|
|Broadcast Receiver|<li>Pub-Sub</li><li>System Broadcast</li><li>Permissions</li><li>Security</li>|
|Content Provider|<li>Content Resolver</li><li>Cursor</li><li>MIME Types</li><li>Contracts</li>|
|Data Storage|<li>App Specific Storage</li><li>Shared Storage</li><li>Preferences</li><li>Database</li><li>Scoped Storage</li><li>LRU Cache</li><li>SQLite</li><li>ROOM</li><li>Data Store</li>|
|Fragments|<li>Fragment Lifecycle</li><li>Dialog Fragment</li><li>Fragment Transactions</li><li>Fragment Manager</li><li>View Lifecycle</li><li>BackStack</li><li>Fragment-Activity Communication</li><li>Fragment-Fragment Communication</li>|
|Navigation Component |<li>Host</li><li>Graph</li><li>Controller</li><li>Back Stacks</li><li>Destinations</li><li>Deeplink</li>|
|Jetpack Components|<li>ViewModel</li><li>LiveData</li><li>Paging</li><li>Lifecycle</li><li>WorkManager</li><li>Data Binding</li>|
|UI |<li>XML</li><li>Jetpack Compose</li>|
|Jetpack Compose|<li>Composition</li><li>ReComposition</li><li>State Hoisting</li><li>Remember</li><li>RememberSaveable</li><li>Side Effects</li><li>LaunchedEffect</li><li>DisposableEffect</li><li>DerivedStateOf</li><li>SnapshotFlow</li><li>CompositionLocal</li><li>Theming</li><li>Modifier</li><li>Layouts</li><li>Box/Column/Row</li><li>Image/painter</li><li>Coil</li><li>LazyColumn/LayRow</li><li>Text/Button/ other ui components</li>|
|Testing|<li>UI Testing</li><li>Unit Testing</li><li>Espresso</li><li>Robolectric</li><li>Mockk</li>|
|Debugging|<li>Logcat</li><li>Timber</li><li>Break Points</li><li>Chucker</li><li>Charles</li><li>LeakCanary</li>|
|Libraries|<li>Retrofit</li><li>OkHttp</li><li>Glide</li><li>Material3</li><li>Hilt</li><li>Dagger</li><li>Retrofit</li>|
|Benchmark|<li>Micro Benchmark</li><li>Macro Benchmark</li>|
|Static Analysis|<li>Ktlint</li><li>Detekt</li><li>Android Lint</li>|
|GitHub Actions|<li>Pipeline</li><li>Build Generation</li><li>Workflow</li>|
|Gradle|<li>Commands</li><li>Groovy</li>|
|Common Errors|<li>ANR</li><li>App Crash</li><li>Fatal Error</li><li>OOM</li><li>ArrayOutOfBound</li>|
|Proguard|<li>Obfuscation</li><li>Keep</li>|
|Code Architecture|<li>MVP</li><li>MVVM</li><li>MVI</li><li>Modularization</li><li>Design Patterns</li><li>Network Layer</li><li>Data Layer</li><li>UI Layer</li><li>Domain/Repository/...</li>|
|Firebase |<li>Crashlytics</li><li>Remote Config</li><li>A/B Testing</li>|
|App Release|<li>App Release Process</li><li>App Distribution</li><li>Google Play Console</li><li>App Review/Ratings</li><li>App Size</li><li>App Policies</li>|


------

## Top 10 Kotlin Coroutines Interview Questions
[- Senior Android Engineer Guide](https://github.com/anandwana001/android-interview/blob/main/Top%2010%20Kotlin%20Coroutines%20Interview%20Questions%20-%20Senior%20Android%20Engineer%20Guide.pdf)


------

## Kotlin Sheet 2024
![](https://github.com/anandwana001/android-interview/blob/main/Kotlin%20Sheet%202024.gif)

## Jetpack Compose Sheet 2024
![](https://github.com/anandwana001/android-interview/blob/main/Jetpack%20Compose%202024.gif)


## Contributing Guidelines
What interesting questions do you face while giving an interview for an Android Engineer role (any level)? Let's open a PR.

## If this Repository helps you, Show your ❤️ by buying me a ☕ below.<br>
<a href="https://www.buymeacoffee.com/anandwana001" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>


## If this repository helps you in any way, show your love :heart: by putting a :star: on this project :v:
