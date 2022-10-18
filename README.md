# Android Engineer Interview Questions

![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/kotlin-%237F52FF.svg?style=for-the-badge&logo=kotlin&logoColor=white)

## Contents

* [Kotlin](#kotlin)
* [Android](#android)
* [Lifecycle](#lifecycle)
* [Networking](#networking)
* [Webview](#webview)
* [Dependency Injection](#dependency-injection)
* [Android Compose](#android-compose)
* [System Design](#system-design)
* [Common Question](#common-question)


## Kotlin
- What is the difference between `const val` and `val`?
- What is so interesting about `data class`?
- Is singleton thread-safe? vs Object?
- What are different type of scope modifiers?
- What are different Coroutine Scope?
- How to manage series and parallel execution?
- Difference between Flow/SharedFlow/StateFlow and elaborate it.
- What happens if we call `.cancel()` from a coroutine scope?
- What is an Init block in Kotlin?
- How to choose between apply and with?
- What is inline function in Kotlin?
- 

## Android
 - How does Garbage collection works?
 - What is a dangling pointer?
 - Elaborate Memory Leak?
 - Explain fragment Lifecycle when it comes to ViewPager and sliding between different fragments.
 - Difference between FragmentStateAdapter and FragmentStatePagerAdapter.
 - Difference between Serializable and Parcelable? What are the disadvantages of Serializable?
 - How you could implement observable SharedPrefs or observable Databases i.e. Observe a certain key/table/query?
 - How does layout inflation work from xml tags to view reference in memory?
 - What is a Thread, Handler, Looper and Message Queue?
 - What are the different methods of concurrency on Android? Can you explain the difference between ExecutorService vs CachedThreadPool vs FixedThreadPool vs AsyncTasks vs HandlerThreads?
 - How does `ViewModel` instance provided to Activity and Fragment. How does `ViewModelProviderStore` decide when to retain the instance?
 - How do you inspect and solve Jank issue? [here](https://developer.android.com/studio/profile/jank-detection)
 - How does the OutOfMemory happens? 
 - How do you find memory leaks in Android applications?
 - What is Doze? What about App Standby? 
 - 
  
### Lifecycle
 - How to keep a video maintain playing state when we rotate screen?
 - How many callbacks in Fragmnets?
 - What could be the reasons when `onPause` didn't get triggered?
 - What kind of events trigger `onPause()` to run?
 - In what scenario does the "onDestory" get called directly after "onCreate"?
 - Which callback gets called on Activity when an AlertDialog is shown?
 - What's the lifecycle in PIP (Picture-in-Picture)?
 - What happens if you rotate the device?
 - Inside a viewpager (Fragment state pager adapter) what will be the lifecycle of the fragments when you swap from tab to another ?
 - Why onActivityCreated is now depreciated in Fragment?
 - Which callback should i use if i want to know when my activity came to foreground?
 - When is onActivityResult called?
 - What does setRetainInstance do and how you can avoid it?
 - What callbacks trigger when a Dialog opens up? Conside both case, dialog attached from same activity/fragment and other activity/fragment.
 - What does `launchWhenCreated`, `launchWhenStarted`, and `launchWhenResumed` functions do?
 - 

### Networking
- What is the role of OkHttp and Retrofit?
- What design pattern does Retrofit use?
- How would optimise handling of access token expiration? How would you handle retry network call when the api fails? (Custom Interceptor response)
- 

### Webview
- What are the problems around security when dealing with `WebView`.
- 

### Dependency Injection
- Provides vs binds
- Subcomponent vs component dependency, what is the difference under the hood
- What is subcomponent and what is the use? How do you use qualifiers or how would you provide different instances of a class with the same data type? Constructor Injection V/s Method Injection? What is the scope? Singleton Annotation?
- What is Circular dependency in dagger?, and how to resolve it
- What's interesting about Hilt?
- Did you use Koin? What are your thoughts on it?
- 

### Android Compose
- How to launch coroutine from a composable function? - [LaunchedEffect](https://www.droidcon.com/2021/10/28/jetpack-compose-side-effects-ii-remembercoroutinescope/)
- How to launch coroutine from a non-composable function, but tied to composition? - [rememberCoroutineScope()](https://www.droidcon.com/2021/10/28/jetpack-compose-side-effects-ii-remembercoroutinescope/)
- What is recomposition? [Recomposition](https://developer.android.com/jetpack/compose/mental-model#recomposition)
- Why and when to use `remember {}`?
- Difference between `LazyColumn` and `RecyclerView`?
- What is AndroidView in compose?
- What is the lifecycle of composeables? [Lifecycle](https://developer.android.com/jetpack/compose/lifecycle)
- How to avoid recomposition of any composable, if the state is not changed? [Smart Recomposition](https://developer.android.com/jetpack/compose/lifecycle#add-info-smart-recomposition)
- What are stable types which can skip recomposition?
- What is State?
- What is MutableState and how does recomposition happens?
- How to retain State accross recomposition and configuration changes?
- Difference between Stateless and Statefull composeables?
- What are your thoughts on flat heirarchy, constraint Layout in compose vs the older view heirarchy in xml
- Difference b/w remember and LaunchedEffect
- Does re-composition of `ComposeItem1` bring any affect on `ComposeItem2`? If yes, then how? 
  - `ComposeParent() { ComposeItem1 {} ComposeItem2() {...} } `
  - What is `CompositionLocal`?


## System Design
 - Design Image Loading Library
 - Design Image Downloading Library
 - Design LRU Cache
 - Design a real-time Twitter feed timeline. How will you structure the backend? Will you use WebSocket or REST for this use case? Justify. 
 - Design Networking Library
 - Design components and overall architecture for a Search feature in an Android application. [Spotify | Android Engineer II | London, UK | Sep 2022]
 - Design a Disk based Cache for client. [Spotify System Design Android/iOS Client]
    ```
    Platform independent 
    Key will be 32 bytes
    Value can be anything but in Byte array
    Cache should be persistent
    Cache should max hold 100k+ Objects
    Cache Max size should be configurable ( Max Size : 10 MB upto 1GB)
    Cache should be opaque
    Cache should be Secure
    ```
  - 

## Common Question
 - `String` vs `StringBuilder`
 - `==` vs `.equals`?
 - `===` vs `==`?
 - To check if strings are rotations of each other or not. And if they are in rotation print the no. of rotations. [Paytm Interview]
 - Find the string is panagram or not [Paytm Interview]

------

## Contributing Guidelines
What interesting questions you had faced while giving interview for Android Engineer role (any level)? Let's open a PR.

## If this repository helps you in anyway, show your love :heart: by putting a :star: on this project :v:
