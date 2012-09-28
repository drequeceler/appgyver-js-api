# Android support

The [Android Preview client](https://play.google.com/store/apps/details?id=com.appgyver.android) currently implements only a part of the appgyver.js API. No Legacy mode APIs are available on the Android.

All [Cordova APIs](http://docs.phonegap.com) (apart from `navigator.notification.vibrate`) do work correctly on Android.

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