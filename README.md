# android-interview

Android Engineer Interview Questions

## Kotlin
- What is the difference between `const val` and `val`?
- What is so interesting about `data class`?
- Is singleton thread-safe? vs Object?
- What are different type of scope modifiers?
- What are different Coroutine Scope?
- How to manage series and parallel execution?
- Difference between Flow/SharedFlow/StateFlow and elaborate it.
- What happens if we call `.cancel()` from a coroutine scope?
- 

## Android
 - How does Garbage collection works?
 - What is a dangling pointer?
 - Explain the terms reference counting, mark and sweep? 
 - Elaborate Memory Leak?
 - Explain fragment Lifecycle when it comes to ViewPager and sliding between different fragments.
 - Difference between FragmentStateAdapter and FragmentStatePagerAdapter.
 - Difference between Serializable and Parcelable? What are the disadvantages of Serializable?
 - How you could implement observable SharedPrefs or observable Databases i.e. Observe a certain key/table/query?
 - How does layout inflation work from xml tags to view reference in memory?
 - How would you go about implementing findViewById? Given 2 view references, how would you go about finding their ancestor view?
   https://obvious.in/blog/deflating-the-layoutinflater-working-with-findviewbyid
 - What is a thread, handler, looper and message queue?
 - What are the different methods of concurrency on Android? Can you explain the difference between ExecutorService vs CachedThreadPool vs FixedThreadPool vs AsyncTasks vs HandlerThreads?
 - How does ViewModel instance is provided to Activity, Fragment. How does ViewModelProviderStore decide when to retain the instance?
  Ans : It uses <Key,Value> to hold onto viewmodel instance, these are removed when ViewModelStore#clear is called. 
  Tip : Look at the accessor of this method to understand how it is retain across configuration changes
 - How do you inspect and solve Jank issue? [here](https://developer.android.com/studio/profile/jank-detection)
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
- What are the problems around security when dealing with webviews.
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
- 


## System Design
 - Design Image Loading Library
 - Design Image Downloading Library
 - Design LRU Cache
 - Design a real-time Twitter feed timeline. How will you structure the backend? Will you use WebSocket or REST for this use case? Justify. 
 - 

## Common Question
 - `String` vs `StringBuilder`
 - 

## Contributing Guidelines
What interesting questions you had faced while giving interview for Android Engineer role (any level)? Let's open a PR.

## If this repository helps you in anyway, show your love :heart: by putting a :star: on this project :v:
