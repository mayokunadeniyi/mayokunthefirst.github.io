---
title: "Instant Weather"
layout: post
date: 2020-05-03 12:51
tag: mvvm pattern, data binding, paging library, aloglia, kotlin coroutines, room, livedata, view model, navigation components, android ktx
headerImage: true
image: ../assets/images/instantweather/instant_weather_512.png
projects: true
hidden: true # don't count this post in blog pagination
description: "An android application that provides real time weather information including forecasts"
category: project
author: mayokunadeniyi
externalLink: false
---

An Android weather application implemented using the MVVM pattern, Retrofit2, LiveData, ViewModel, Coroutines, Room, Navigation Components, Data Binding and some other libraries from the [Android Jetpack](https://developer.android.com/jetpack/).

---

## Preview
<p><a><img src="/assets/images/instantweather/instant_weather_github.png"></a></p>

<a href='https://play.google.com/store/apps/details?id=com.mayokunadeniyi.instantweather&pcampaignid=pcampaignidMKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1'><img alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png' width="280"/></a>
---

## Architecture
The architecture of this application relies and complies with the following points below:
* A single-activity architecture, using the [Navigation Components](https://developer.android.com/guide/navigation) to manage fragment operations.s
* Pattern [Model-View-ViewModel](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel)(MVVM) which facilitates a separation of development of the graphical user interface.
* [Android architecture components](https://developer.android.com/topic/libraries/architecture/) which help to keep the application robust, testable, and maintainable.

<p align="center"><a><img src="https://raw.githubusercontent.com/mayokunthefirst/Instant-Weather/master/media/final-architecture.png" width="700"></a></p>

---

## Technologies

* [Retrofit](https://square.github.io/retrofit/) a REST Client for Android which makes it relatively easy to retrieve and upload JSON (or other structured data) via a REST based webservice.
* [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel) to store and manage UI-related data in a lifecycle conscious way.
* [LiveData](https://developer.android.com/topic/libraries/architecture/livedata) to handle data in a lifecycle-aware fashion.
* [Navigation Component](https://developer.android.com/guide/navigation) to handle all navigations and also passing of data between destinations.
* [Timber](https://github.com/JakeWharton/timber) - a logger with a small, extensible API which provides utility on top of Android's normal Log class.
* [Algolia Search API - Android](https://www.algolia.com/doc/guides/building-search-ui/getting-started/android/) to quickly and seamlessly implement search within the application.
* [Material Design](https://material.io/develop/android/docs/getting-started/)
* [Coroutines](https://kotlinlang.org/docs/reference/coroutines-overview.html) used to manage the local storage i.e. `writing to and reading from the database`. Coroutines help in managing background threads and reduces the need for callbacks.
* [Data Binding](https://developer.android.com/topic/libraries/data-binding/) to declaratively bind UI components in layouts to data sources.
* [Room](https://developer.android.com/topic/libraries/architecture/room) persistence library which provides an abstraction layer over SQLite to allow for more robust database access while harnessing the full power of SQLite.
* [Paging Library](https://developer.android.com/topic/libraries/architecture/paging) helps you load and display small chunks of data at a time.
* [Android KTX](https://developer.android.com/kotlin/ktx) which helps to write more concise, idiomatic Kotlin code.
* [Preferences](https://developer.android.com/guide/topics/ui/settings) to create interactive settings screens.


---

Check it out [here](https://github.com/mayokunthefirst/Instant-Weather).
If you need help, just let me know by [opening an issue](https://github.com/mayokunthefirst/Instant-Weather/issues) or down below in the comments section.
