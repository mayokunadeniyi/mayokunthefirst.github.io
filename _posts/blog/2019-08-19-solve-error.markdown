---
title: Solving error code:12500, Google Sign-in auth
layout: post
date: 2019-08-04 04:33
headerImage: false
tag:
- google sign-in
- authentication
- firebase
- google api console
- errors
- android
star: true
category: blog
author: mayokunadeniyi
description: How to fix error code:12500 when implementing authentication with Google Sign-in.
---
<p align="center"><a><img class="image" src="{{ site.url }}/assets/images/errorimage.png" alt="jekyll" style="width:80%"></a></p>

Errors:bangbang: They suck right? I was building an Android application with Firebase that uses Google Sign-in to perform authentication and on testing it out, I got this error code:12500. Oh well, I headed out to the [documentation](https://developers.google.com/android/reference/com/google/android/gms/auth/api/signin/GoogleSignInStatusCodes) to seek for help and what I saw was not really helpful:
<p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/errorStuff.png?raw=true" width="95%" height="190"></a></p>
<figcaption class="caption">Screenshot from Google Developers Documentation</figcaption>

---

Note:
* The solutions below assumes you have added the SHA-1 (certificate fingerprint) for your application to the Firebase project. If not, check [this](https://stackoverflow.com/questions/39144629/how-to-add-sha-1-to-android-application) out
* The solutions below are in reference to Android Studio, Firebase and the Google Developer Console

---

## :wrench: How to Fix

**1. Check if Google Sign-in is enabled on Firebase**

Head over to your Firebase console, under Authentication >> Sign-in method, check if you enabled Google Sign-in for your application just like the image below

<p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/ImagesError12500/fixImage1.png?raw=true" width="95%" height="200"></a></p>

After this, rebuild and run your application to check if Google Sign-in works now. If it doesn't proceed to the next step.


**2. Check if project support email is configured**

Still in your Firebase console, under Authentication >> Sign-in method, and having enabled Google Sign-in, select the Google Sign-in option. Check to the if there is a project support email added to the project if not, add one and save it.

<p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/ImagesError12500/fixImage2.png?raw=true" width="95%" height="250"></a></p>

After this, rebuild and run your application to check if Google Sign-in works now. If it doesn't proceed to the next step.


**3. Check if authorized domains in the [Google Cloud Platform](https://console.developers.google.com/apis/) console matches the ones in your Firebase console**

Still in your Firebase console, under **Authentication >> Sign-in method**, with Google Sign-in enabled, scroll down to the Authorized Domain section just below Sign-in providers and note down the authorized domains. 

<p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/ImagesError12500/fixImage3.png?raw=true" width="95%" height="230"></a></p>

In a new tab, open up  [Google Cloud Platform](https://console.developers.google.com/apis/) and select your Firebase project name.

*If your project is not being displayed, search for it using search bar up above*

With your project selected, on the left nav bar, under **Credentials >> OAuth consent screen**, scroll down to the authorized domain section. *Excluding localhost* in the authorized domains in your Firebase console, make sure the authorized domains in the Firebase console and Google Cloud Platform console match if not, copy the domains in the Firebase console and add to the authorized domains for your project in the Google Cloud Platform console.

<p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/ImagesError12500/fixImage5.png?raw=true" width="95%" height="250"></a></p>

*Most times, the second domain in the Google Cloud Platform is always made short to read '**web.app**'. It is the same as the domain ending with '**project_name.web.app**' in your Firebase console*

After this, rebuild and run your application to check if Google Sign-in works now. If it doesn't proceed to the next step.

**4. Add an application logo to your project in the [Google Cloud Platform](https://console.developers.google.com/apis/) console**

In your Google Cloud Platform, with your project selected, on the left nav bar, under **Credentials >> OAuth consent screen**, scroll down to the application logo section, add the application logo and save. 

<p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/ImagesError12500/fixImage1.png?raw=true" width="95%" height="200"></a></p>

Rebuild and run your application to check if Google Sign-in now works. After these 4 steps, incase you're still experiencing the same error:12500, do send me a DM on [Twitter](https://twitter.com/mayokunadeniyi). Thank you for your time :thumbsup:










