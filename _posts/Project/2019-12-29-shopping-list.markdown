---
title: "Shopping List"
layout: post
date: 2019-12-28 17:51
tag: mvvm, data binding, kotlin coroutines, room, livedata, view model, navigation components, android ktx
headerImage: true
image: ../assets/images/shoppinglist-logo.png
projects: true
hidden: true # don't count this post in blog pagination
description: "Keep track of items needed when shopping"
category: project
author: mayokunadeniyi
externalLink: false
---

An Android application that integrates the [Android Jetpack](https://developer.android.com/jetpack/) components to help keep track of items needed when shopping. This application was implemented using MVVM pattern, LiveData, ViewModel, Kotlin-Coroutines, Room, Navigation Components and DataBinding.

---

## Quick Demo
<p align="center"><a><img src="/assets/images/gifdemo.gif" width="300"></a></p>


---

## Architecture
The architecture of this application relies and complies with the following points below:
* A single-activity architecture, using the [Navigation Components](https://developer.android.com/guide/navigation) to manage fragment operations.
* Pattern [Model-View-ViewModel](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel)(MVVM) which facilitates a separation of development of the graphical user interface.
* [Android architecture components](https://developer.android.com/topic/libraries/architecture/) which help to keep the application robust, testable, and maintainable.

---

## Technologies

* [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel) to store and manage UI-related data in a lifecycle conscious way.
* [LiveData](https://developer.android.com/topic/libraries/architecture/livedata) to handle data in a lifecycle-aware fashion.
* [Navigation Component](https://developer.android.com/guide/navigation) to handle all navigations and also passing of data between destinations.
* [Timber](https://github.com/JakeWharton/timber) - a logger with a small, extensible API which provides utility on top of Android's normal Log class.
* [Kotlin Coroutines](https://kotlinlang.org/docs/reference/coroutines-overview.html) for managing background threads and reducing needs for callbacks.
* [Data Binding](https://developer.android.com/topic/libraries/data-binding/) to declaratively bind UI components in layouts to data sources.
* [Room](https://developer.android.com/topic/libraries/architecture/room) persistence library which provides an abstraction layer over SQLite to allow for more robust database access while harnessing the full power of SQLite.

#### Testing
* [JUnit](https://junit.org/junit4/) - a simple framework to write repeatable tests.

---

Check it out [here](https://github.com/mayokunthefirst/Shopping-List).
If you need help, just let me know by [opening an issue](https://github.com/mayokunthefirst/Shopping-List/issues) or down below in the comments section.
