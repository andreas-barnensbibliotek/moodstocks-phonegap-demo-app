# Moodstocks SDK - PhoneGap sample apps

PhoneGap plugins and sample applications for the Moodstocks SDK. So far we only support the iOS platform (tested with PhoneGap v2.3). This repository is made of:

* `www`: the demo (common to iOS and Android environments)
* `ios`: the specific PhoneGap project for iOS
* `android`: the specific PhoneGap project for Android

Each of them contains a detailed README to help you get started.

## Feature: Web view as overlay!

Generally speaking, we take the default web view and insert it into our scanner view.

  * You can personalize the overlay very easily. Just modify the html content inside the div `#overlayContainer` in `index.hmtl`

  * UI toggle.
    * When the scanner is launched, in order to have an overlay floating above the camera view you need to hide the menu.

    ```javascript
    // When scanner is launched, hide the menu and show the overlay
    function scannerOn() {
        overlayContainer.style.display = "inline";
        menuContainer.style.display = "none";
    }
    ```

    * Correspondingly when the scanner is dismissed you need to restore the menu and hide the overlay.

    ```javascript
    // When scanner is dismissed, display the menu and hide the overlay
    function scannerOff() {
        overlayContainer.style.display = "none";
        menuContainer.style.display = "inline";
    }
    ```

    > Workaround for the background color: Don't put apply any css to the container that you need to hide.

## Help

Need help? Check out our [Help Center](http://help.moodstocks.com/).

## Copyright

Copyright (c) 2013 [Moodstocks SAS](http://www.moodstocks.com)
