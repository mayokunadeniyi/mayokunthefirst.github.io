---
title: "Card Info Finder"
layout: post
date: 2020-08-19 09:06
tag: clean-architecture, mvvm, dependency-injection, retrofit2, kotlin-coroutines, koin, room, mockito, junit, mlkit, firebase, DataBinding, Android
headerImage: true
image: ../assets/images/cardinfo/cardinfologo.png
projects: true
hidden: true # don't count this post in blog pagination
description: "A multi-modular Android application implemented using Clean Architecture, MVVM pattern, Koin, Kotlin Coroutines, Retrofit2, Room etc.. to identify the institution that issued a payment card"
category: project
author: mayokunadeniyi
externalLink: false
---

A Multi-modular Android application implemented using Clean Architecture, MVVM pattern, Koin for Dependency Injection, Kotlin Coroutines, Retrofit2, Room etc.. to identify the institution that issued a payment card. This application allows the user to provide the number either by entering a card number using the Soft Input keyboard or by Scanning the payment card number using the on-device OCR functionality. 

---
## Project Characteristics

* 100% [Kotlin](https://kotlinlang.org/)
* Modern architecture (Clean Architecture, Model-View-ViewModel)
* [Android Jetpack](https://developer.android.com/jetpack)
* A single-activity architecture ( using the [Navigation component](https://developer.android.com/guide/navigation/navigation-getting-started) to manage Fragment operations.)
* CI pipeline ([GitHub Actions](https://github.com/features/actions))
* Testing (Unit, UI)
* Dependency Injection
* Material design

<p align="center"><a><img src="../assets/images/cardinfo/app-demo.gif" width="300"></a></p>
---

## Architecture
Clean Architecture is the "core architecture" of this application. The main purpose of this approach is to achieve a separation of concerns which Clean architecture helps with and in
making the code loosely coupled. This approach results in a more testable and flexible code. This approach divides the project in 3 modules: **presentation, data and domain**.

<p align="center"><a><img src="../assets/images/cardinfo/clean-arch.png" width="500"></a></p>

* **Presentation**: Layer with the Android Framework, the MVVM pattern and the DI module. Depends on domain to access the use cases and on DI, to inject dependencies. This is the layer closest 
to what the user sees on the screen. 
    - **MVVM**: The Model View ViewModel pattern helps with the separation of concerns, dividing the user interface with the logic behind. It combines very well with Android Architecture Components like LiveData and DataBinding.
* **Domain**: This is the core layer of the application with the business logic. It contains the use cases, in charge of calling the correct repository or data member.The domain layer is independent of any other layers. 
* **Data**: Layer with the responsibility of managing the application data and exposes these data sources as repositories to the domain layer. Typical responsibilities of this layer is to retrieve data from the internet and optionally cache this data locally.

---

## Technologies
* [Kotlin](https://kotlinlang.org/) + [Coroutines](https://kotlinlang.org/docs/reference/coroutines-overview.html) - perform background operations
* [Koin](https://insert-koin.io/) - dependency injection
* [Retrofit](https://square.github.io/retrofit/) - networking
* [Jetpack](https://developer.android.com/jetpack)
    * [Navigation](https://developer.android.com/topic/libraries/architecture/navigation/) - deal with whole in-app navigation
    * [LiveData](https://developer.android.com/topic/libraries/architecture/livedata) - notify views about database change
    * [Lifecycle](https://developer.android.com/topic/libraries/architecture/lifecycle) - perform an action when lifecycle state changes
    * [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel) - store and manage UI-related data in a lifecycle conscious way
    * [Data Binding](https://developer.android.com/topic/libraries/data-binding/) - declaratively bind UI components in layouts to data sources.
    * [Room](https://developer.android.com/topic/libraries/architecture/room) persistence library which provides an abstraction layer over SQLite
* [Glide](https://bumptech.github.io/glide/l) - image loading library
* [Firebase ML Kit](https://developers.google.com/ml-kit) uses the On-Device API to recognize the numbers on the payment card
* [and more...](https://github.com/mayokunthefirst/CardInfoFinder/blob/master/buildSrc/src/main/kotlin/Dependencies.kt)
* Tests
    * [Unit Tests](https://en.wikipedia.org/wiki/Unit_testing) ([JUnit](https://junit.org/junit4/))
    * [Mockito](https://site.mockito.org/)
    * [Espresso](https://developer.android.com/training/testing/espresso)
* Gradle
    * [Gradle Kotlin DSL](https://docs.gradle.org/current/userguide/kotlin_dsl.html)
    * Plugins ([SafeArgs](https://developer.android.com/guide/navigation/navigation-pass-data#Safe-args))


---

Check it out [here](https://github.com/mayokunthefirst/CardInfoFinder).
If you need help, just let me know by [opening an issue](https://github.com/mayokunthefirst/CardInfoFinder/issues) or down below in the comments section.
