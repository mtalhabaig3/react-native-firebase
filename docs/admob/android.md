---
title: Android Installation
description: Manually integrate AdMob into your Android application.
---

# Android Manual Installation

The following steps are only required if you are using React Native <= 0.59 or need to manually integrate the library.

#### Update Gradle Settings

Add the following to your projects `/android/settings.gradle` file:

```groovy
include ':@react-native-firebase_admob'
project(':@react-native-firebase_admob').projectDir = new File(rootProject.projectDir, './../node_modules/@react-native-firebase/admob/android')
```

#### Update Gradle Dependencies

Add the React Native Firebase module dependency to your `/android/app/build.gradle` file:

```groovy{3}
dependencies {
  ...
  implementation project(path: ":@react-native-firebase_admob")
}
```

#### Add package to the Android Application

Import and apply the React Native Firebase module package to your `/android/app/src/main/java/**/MainApplication.java` file:

Import the package:

```java
import io.invertase.firebase.admob.ReactNativeFirebaseAdMobPackage;
```

Add the package to the registry:

```java{4}
protected List<ReactPackage> getPackages() {
  return Arrays.asList(
    new MainReactPackage(),
    new ReactNativeFirebaseAdMobPackage(),
```

#### Rebuild the project

Once the above steps have been completed, rebuild your Android project:

```bash
react-native run-android
```
