# Moodstocks PhoneGap plugin for Android

Moodstocks [PhoneGap](http://phonegap.com/) plugin for Android platform enables developers to embed Moodstocks scanner into a PhoneGap application. Along with the plugin we provide a sample application to help you get started.

## Prerequisites

* Android development environment.
* A Moodstocks [developer account](https://developers.moodstocks.com/register).
* [PhoneGap v2.3.0](http://phonegap.com/download/) downloaded.

> IMPORTANT: the sample application has been tested with PhoneGap v2.3.0. You might encounter some errors if you use a lower version.

## Test the demo

0. Get [Moodstocks PhoneGap plugin for Android](https://github.com/Moodstocks/moodstocks-phonegap-plugin/android)

  > NOTE: Our PhoneGap plugin is composed by
    * MoodstocksPlugin.js
    * MoodstocksPlugin.java
    * MoodstocksScanActivity.java
    * MoodstocksWebView.java: it extends the `CordovaWebView` in order to perform properly in our scanner.
    * Demo.java: it overrides a part of `DroidGap` in order to implement our web view overlay logic.
    * Resources related to these 2 activity

1. Git clone this repo.
2. Import our demo project into your preferred IDE.

3. Set up the Moodstocks SDK: please refere to this [step-by-step tutorial](https://developers.moodstocks.com/doc/tuto-android/1).

4. Copy all the files inside `www` folder to `android/Demo/assets/www`.
4. Copy `MoodstocksPlugin.js` into `android/Demo/assets/www/js`.
4. Copy these files into package `com.moodstocks.phonegap.plugin`:
  * MoodstocksPlugin.java
  * MoodstocksScanActivity.java
  * MoodstocksOverlay.java
4. Replace `Demo.java` in `com.moodstocks.phonegap.demo` by `Demo.java` in our plugin folder.

5. Configure your API key & secret in `MoodstocksPlugin.java` which can be found inside the package `com.moodstocks.phonegap.plugin`

  ```
  //--------------------------------
  // Moodstocks API key/secret pair
  //--------------------------------
  private static final String API_KEY = "";
  private static final String API_SECRET = "";
  ```

6. Build and run the application on your android device.

## Create your own project from scratch

If you've never used PhoneGap before, please check out their [Android Get Started guide](http://docs.phonegap.com/en/2.5.0/guide_getting-started_android_index.md.html#Getting%20Started%20with%20Android) first!.

1. Create a PhoneGap project, for example:

  ```console
  ./create <project_folder_path> com.example.phonegap.demo Demo
  ```

2. Set up Moodstocks SDK. (see point 3 in the section above)

3. Create a package called `com.moodstocks.phonegap.plugin` and copy these files into it:
  * MoodstocksPlugin.java
  * MoodstocksScanActivity.java
  * MoodstocksOverlay.java

4. Replace your main activity class `Demo.java` of package `com.example.phonegap.demo` by our `Demo.java` in the plugin folder.

4. Add related resources of `MoodstocksScanActivity.java` and `MoodstocksOverlay.java` into your project
  * Copy `scan.xml` into `res/layout`
  * Add this line in `res/values/strings.xml`

    ```xml
    <string name="scan_name">ScanActivity</string>
    ```

  * Add activity declaration into your `AndroidManifest.xml`

    ```xml
    <activity
        android:name="com.moodstocks.phonegap.plugin.MoodstocksScanActivity"
        android:label="scan_name"
        android:screenOrientation="portrait"
        android:theme="@android:style/Theme.NoTitleBar.Fullscreen">
    </activity>
    ```

5. Add MoodstocksPlugin's mapping in `res/xml/config.xml`

  ```xml
  <plugin name="MoodstocksPlugin" value="com.moodstocks.phonegap.plugin.MoodstocksPlugin" />
  ```

6. Refer to `www/index.html` in our demo as an example and create your own applications
7. Configure your API key & secret in `MoodstocksPlugin.java`.
7. Then you can launch your application!

## Help

Need help? Check out our [Help Center](http://help.moodstocks.com/).

## Copyright

Copyright (c) 2013 [Moodstocks SAS](http://www.moodstocks.com)

