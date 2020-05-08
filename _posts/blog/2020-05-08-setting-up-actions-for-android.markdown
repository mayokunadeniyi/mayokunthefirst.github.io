---
title: Setting up GitHub Actions for Android Projects with several API keys.
layout: post
date: 2020-05-08 14:15
image: /assets/images/github_actions.png
headerImage: true
tag:
- android
- github actions
- continous integration
- continous delivery
category: blog
author: mayokunadeniyi
description: How to setup CI/CD using GitHub Actions for Android projects that utilize several API keys.
---
 
 If you are familiar with the concept of [CI/CD](https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment), you would agree that [GitHub Actions](https://github.com/features/actions) is one of the best things to happen in this field as it makes it so easy to automate your software workflows. You get to build, test, and deploy your code right from GitHub and this is what makes it so cool.

While I was building [Instant Weather](https://github.com/mayokunthefirst/Instant-Weather), I setup the project without a CI/CD tool and this only dawned on me when the project got its first Pull Request. This post would explain how I integrated GitHub Actions into the live project and how you can do so for any of your Android projects.

---

In the world of Android development, we are always consuming one [API](https://en.wikipedia.org/wiki/Application_programming_interface) or the other which we connect to using a key. In the process of open-sourcing our projects, we definitely can not expose these API keys to the public. In an attempt to hide the API keys Instant Weather uses, I used [Gradle](https://gradle.org/) to secure these API keys. You can check this [article](https://medium.com/@abhishekdubey_70837/using-gradle-to-secure-app-keys-in-android-9d2796ca4007) on how to get this done. Now let's walk through how I setup GitHub Actions for my live project.

## Step 1
The first step was to create a new branch in the project and checkout that branch. A simple "`git checkout -b new-branch-name`". After which I created `.github\workflows\` directory in the root of the Android project. In that same directory, I created the workflow file. I named this workflow file `android_build.yml`. The file uses the [YAML](https://en.wikipedia.org/wiki/YAML) file extension.
<p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/GitHub-Actions/pic1.png?raw=true" style="width:80%"></a></p>

## Step 2
Next step was to write out the content for the workflow file starting with the `name`. This `name` should match the workflow file's name. After which I defined when I wanted this workflow file to be executed using the `on` key which were when a Pull Request was made or when a push occurs to the repository. By now we have something like this:

```
name: Android Build

on: [push, pull_request]
```

## Step 3
Next step was to define the `jobs` that would run when the workflow is triggered. We use the `jobs` keyword to define this. A Job is basically an environment with a task or several tasks. Note, every workflow must have at least a Job. Now we have something like this:

```
name: Android Build

on: [push, pull_request]

jobs:
  build:

    runs-on: ubuntu-latest
```
I want this to run on the pre-installed runner `ubuntu-latest` and I indicated this using the `runs-on` keyword.

## Step 4
After defining the environment, the next step was to define the tasks that would be run during the build. We make use of the `steps` keyword to achieve this. 

- The first task was to checkout the code in context. I made use of a prebuilt action `actions/checkout@v2` to achieve this. Now we mark this step with the `uses` keyword.

- Instant Weather makes use of [Open Weather](https://openweathermap.org/) and [Algolia](https://www.algolia.com/doc/) and utilizing these services require some API keys and an ID. I secured these keys with Gradle, check this [article](https://medium.com/@abhishekdubey_70837/using-gradle-to-secure-app-keys-in-android-9d2796ca4007) on how to achieve this, and added a build config field for these keys. Hence, the project will not build successfully if the file `apikeys.properties` was missing and also if the content was empty. To tackle this, I included a task that would create the file, create these API key fields and assign dummy values to these fields. 

```
 - name: Create apikey.properties
        run: |
          cat <<EOF> apikey.properties
          API_KEY = "API_KEY"
          ALGOLIA_API_KEY = "ALGOLIA_API_KEY"
          ALGOLIA_APP_ID = "ALGOLIA_APP_ID"
          EOF
```

- The next step was to create a task to configure the JDK for the Android build. I made use of an inbuilt action `actions/setup-java@v1` and indicated the Java version, in this case, 1.8.

```
- name: Set Up JDK
        uses: actions/setup-java@v1
        with:
         java-version: 1.8
```

- The next step was to define the Gradle build tasks that would run to verify the project's build status. Here we would make use of our normal Gradle commands. We want to run `test` and `assemble` on our project. We do this by creating two separate tasks with the suitable commands to achieve this. 

```
- name: Run Tests
        run: ./gradlew test

      - name: Build Project
        run: ./gradlew assemble
```

Wrapping this up, we should have this by now: 

```
name: Android Build

on: [push, pull_request]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2

      - name: Create apikey.properties
        run: |
          cat <<EOF> apikey.properties
          API_KEY = "API_KEY"
          ALGOLIA_API_KEY = "ALGOLIA_API_KEY"
          ALGOLIA_APP_ID = "ALGOLIA_APP_ID"
          EOF

      - name: Set Up JDK
        uses: actions/setup-java@v1
        with:
         java-version: 1.8

      - name: Run Tests
        run: ./gradlew test

      - name: Build Project
        run: ./gradlew assemble
```

## Final Step
Now, we have successfully written out a simple workflow for our project. You can validate the syntax of this YAML file using the [YAML Lint](http://www.yamllint.com/) tool. GitHub Actions would only recognize this workflow if it's in our `master` branch. The final step was to save all our changes `git add .`, commit the changes `git commit -m "Commit message"` and push to the current branch I was working on. I then proceeded to GitHub, created a Pull Request from that branch and merged it into my `master` branch. Having done this, we would have setup GitHub Actions for our repository. Any commit we push to the repository, or a Pull Request made to the repository would trigger our workflow as we have set it to. And voila! we have this:

<p align="center"><a><img src="https://github.com/mayokunthefirst/mayokunthefirst.github.io/blob/master/assets/images/GitHub-Actions/pic2.png?raw=true" style="width:80%"></a></p>

Incase you are experiencing any issue setting this up, [Nate Ebel](https://twitter.com/n8ebel) has a good tutorial on YouTube to help you understand. Check it out [here](https://www.youtube.com/watch?v=dFHV5KsX6Xw). You can also send me a message on [Twitter](https://twitter.com/mayokunadeniyi). Thank you for your time :thumbsup: