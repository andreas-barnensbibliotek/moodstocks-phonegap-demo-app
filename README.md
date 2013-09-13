# Moodstocks SDK - PhoneGap demo apps

This repository is made of:

* `www`: the demo (common to iOS and Android environments)
* `ios`: the specific PhoneGap project for iOS
* `android`: the specific PhoneGap project for Android

Each of them contains a detailed README to help you get started.

## Feature: Web view as overlay!

Instead of using a native overlay to display help information, we take advantage of PhoneGap and use a web view as an overlay.

  * You can personalize the overlay very easily. Just modify the html content inside the div `#overlayContainer` in `index.html`

  * You need to do a UI toggle to use it correctly.
    * When the scanner is launched, in order to have an overlay floating above the camera view you will need to hide the menu. This is what we do in our demo:

    ```javascript
    // When scanner is launched, hide the menu and show the overlay
    function scannerOn() {
        overlayContainer.style.display = "inline";
        menuContainer.style.display = "none";
    }
    ```

    * Correspondingly when the scanner is dismissed you will need to restore the menu and hide the overlay:

    ```javascript
    // When scanner is dismissed, display the menu and hide the overlay
    function scannerOff() {
        overlayContainer.style.display = "none";
        menuContainer.style.display = "inline";
    }
    ```

    > Workaround for the background color issue: Don't put apply any css to the container that you need to toggle.


Here are some screenshots of our basic PhoneGap demo:

![screenshot_phonegap_demo](http://www.moodstocks.com/wp-content/uploads/2013/09/phonegap_demo.png)


If you are looking for something more interactive, for example, display scan result on the overlay, you can check out [our Sencha Touch Demo](https://github.com/Moodstocks/moodstocks-sencha-demo-app).

## Help

Need help? Check out our [Help Center](http://help.moodstocks.com/).

## Copyright

Copyright (c) 2013 [Moodstocks SAS](http://www.moodstocks.com)
