# Moodstocks PhoneGap Demo for iOS

Moodstocks [PhoneGap](http://phonegap.com/) plugin for iOS platform enables developers to embed Moodstocks scanner into a PhoneGap application. Along with the plugin we provide a sample application to help you get started.

## Prerequisites

* iOS development environment.
* A Moodstocks [developer account](https://developers.moodstocks.com/register).
* [PhoneGap](http://phonegap.com/download/) downloaded.

> IMPORTANT: the sample application has been tested with PhoneGap v2.3.0 ~ v.2.8.0. You might encounter some errors if you use a lower version.

## Test the demo

[Moodstocks PhoneGap plugin](https://github.com/Moodstocks/moodstocks-phonegap-plugin/) has been configured as a submodule of this repo.

1. Git clone this repo.

2. Initialize and update submodule - `plugin`

  ```console
  $ git submodule init
  $ git submodule update
  ```

3. Open the `www` folder and copy everything to `ios/Demo/www/`.

4. Open the `plugin` folder and copy `MoodstocksPlugin.js` into `ios/Demo/www/js/`.

5. `open ios/Demo/Demo.xcodeproj/`

6. Set up [Moodstocks SDK for iOS](https://developers.moodstocks.com/downloads) in this Xcode project.

  > NOTE: a detailed [How-To](https://developers.moodstocks.com/doc/tuto-ios/1) can be found in our Developers Center.

7. Configure your API key and API secret in `Plugins/MoodstocksPlugin.m`.

  ```objective-c
    #define MS_API_KEY @"ApIkEy"
    #define MS_API_SEC @"ApIsEcReT"
  ```

8. Build and run the application on your device.

## Create your own project from scratch

If you've never used PhoneGap before, please check out their [iOS Get Started guide](http://docs.phonegap.com/en/2.3.0/guide_getting-started_ios_index.md.html#Getting%20Started%20with%20iOS) first!.

Then:

0. Get [Moodstocks PhoneGap plugin for iOS](https://github.com/Moodstocks/moodstocks-phonegap-plugin/ios)

  > NOTE: Our PhoneGap plugin is composed by
    * MoodstocksPlugin.js
    * MoodstocksPlugin.{h,m}
    * Other native resources:
      * MSScannerController.{h,m}
      * MSHandler.{h,m}

1. Create a PhoneGap project.

2. Set up [Moodstocks SDK for iOS](https://developers.moodstocks.com/downloads) in your Xcode project.

3. Click on your project > `TARGETS` > `Build Phases` tab, then open the list of `Link Binary With Libraries` and add `CoreVideo.framework` to your library. Then make sure you have all these 4 libraries in the list:
  * AVFoundation.framework
  * CoreMedia.framework
  * CoreVideo.framework
  * QuartzCore.framework

4. Copy the files below into the corresponding folders in your project :
  * Copy `MoodstocksPlugin.js` to `/path/to/project/www/js`
  * Open Xcode and drag drop `MoodstocksPlugin.h`, `MoodstocksPlugin.m` and other native resources files(`MSScannerController.{h,m}`, `MSHandler.{h,m}`) to `/path/to/project/YourProjectName/Plugins` in your project

5. Add our plugin under the ```<plugins>``` tag of your project's `config.xml` file.

  ```xml
  <plugin name="MoodstocksPlugin" value="MoodstocksPlugin" />
  ```

6. Update your API key and API secret in `MoodstocksPlugin.m`.

7. Construct your application (a.k.a the `www` folder) by using different web technologies. Refer to `index.html` in our sample project if you are not sure how to use the plugin.

7. Build and run the application on your device.

## Help

Need help? Check out our [Help Center](http://help.moodstocks.com/).

## Copyright

Copyright (c) 2013 [Moodstocks SAS](http://www.moodstocks.com)
