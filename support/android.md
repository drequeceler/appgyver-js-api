# Android support

The [Android Preview app](https://play.google.com/store/apps/details?id=com.appgyver.android) currently implements only a part of the appgyver.js API. Furthermore, the current version of [AppGyver Toolbelt](http://www.appgyver.com/toolbelt) is designed to work with the presently iOS-only [AppGyver Scanner app](https://itunes.apple.com/app/appgyver-scanner/id575076515?mt=8). 

Even though the latest AppGyver Studio only serves a QR code for Local Preview, you can still input your computer's IP address into the Android Preview app to connect it to AppGyver Studio and get the Preview flow working.

All [Cordova APIs](http://docs.phonegap.com) (apart from `navigator.notification.vibrate`) do work correctly on Android. The Android runtime uses Cordova version 2.0.0. On Android, the `cordova-2.0.0.js` must be loaded from a local directory.

## Supported API calls

Methods written in ~~strikethrough~~ are deprecated in favor of the [Cordova API](http://docs.phonegap.com).

* [~~AG.camera.choosePicture~~](../topics/camera/methods/choosePicture.md)
* [~~AG.device.getLocale~~](../topics/device/methods/getLocale.md)
* [AG.events.addEventListener](../topics/events/methods/addEventListener.md) 
* [AG.events.removeAllEventListeners](../topics/events/methods/removeAllEventListeners.md)
* [~~AG.file.download~~](../topics/file/methods/download.md)
* [AG.file.preview](../topics/file/methods/preview.md)
* [AG.file.unzip](../topics/file/methods/unzip.md)
* [~~AG.GUI.alert~~](../topics/GUI/methods/alert.md)