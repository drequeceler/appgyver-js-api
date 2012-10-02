# appgyver.js API documentation, version 0.9.2

As of version 0.9.2, AppGyver uses [Apache Cordova](http://incubator.apache.org/cordova/) (also distributed as PhoneGap) as the main native bridge between your JavaScript code and the native wrapper app. You must include Cordova's JavaScript library to all HTML documents in an AppGyver app: simply add a `<script src="http://localhost:13101/cordova-2.0.0.js"></script>` tag in your HTML document's `<head>` tag, before any Cordova API calls.

**We've deprecated most of the old `appgyver.js` APIs in favor of Cordova.** Please see the [Cordova API documentation](http://docs.phonegap.com) for a list of supported APIs.

However, there are some things that Cordova doesn't provide, so `appgyver.js` remains to give you access to AppGyver's native UI elements, navigation magic and other enhancements and abstractions. The `appgyver.js` library is available in the `Application/appgyver/` folder on your mobile device. So, if your HTML document is `MY_PROJECT/views/default/index.html`, the tag to load the library file is `<script src="../appgyver/appgyver.js"></script>`.

Also, several APIs are only available in Legacy mode, which can be enabled from the Preview app's settings (accessible through the Settings app on iOS).

The [deprecated and Legacy mode APIs](deprecated/index.md) are still available for reference, but no support is provided for them.

## Topics

* [AG.ajax](topics/ajax/ajax.md)
* [AG.camera](topics/camera/camera.md)
* [AG.device](topics/device/device.md)
* [AG.events](topics/events/events.md)
* [AG.file](topics/file/file.md)
* [AG.GUI](topics/GUI/GUI.md)
* [AG.parameters](topics/parameters/parameters.md)

## Webviews and layers

AppGyver renders an app's HTML5 content in WebKit-powered **webviews**. Basically, each webview is a mobile browser without any of the browser's UI elements. Thus, everything that works on a WebKit-based mobile browser will work in AppGyver: all CSS3 stuff, `<canvas>` elements, third-party JavaScript libraries and so on.

An AppGyver app can run multiple webviews concurrently, although only one webview is shown at a time. The other webviews stay active in the background: JavaScript continues to run, scroll position stays the same etc. It's like leaving a browser tab open.

AppGyver apps can run concurrent views in two ways: as **tab bar tabs** or as **layers**

### openLayer

When the [`AG.GUI.openLayer`](topics/GUI/methods/openLayer.md) method is called (either programmatically or by clicking on an `<a>` tag; see *Navigation extension* below), a new webview opens on top of the current one as a **layer**, complete with a native transition animation. 
  
The target HTML document is rendered inside the new webview, while the original webview stays active and open under the layer. 

When you call the [`AG.GUI.popLayer`](topics/GUI/methods/popLayer.md) method, the topmost layer is removed with an animation and the layer underneath becomes the one that is rendered. Think of it as laying down a sheet of paper on top of the current view and removing it.

When you call the openLayer method without any parameters, the native navigation bar appears with the native back button. Clicking the back button effectively calls `popLayer` for the current layer, returning you to the webview underneath.

### Tab bars

On iOS, AppGyver apps can use the native tab bar for navigation. To enable the tab bar, the value of the `fullscreen` key in `application.json` must be set to `false`, and the project must have at least one tab bar tab defined.

Each tab bar tab is an independent stack of webview layers. Thus, the state of any webviews (visible or hidden beneath the topmost layer) are preserved when the user switches to another tab and back.

A tab bar tab points to an initial HTML document that will be loaded into the webview when the user starts the app.

### Navigation extension

The appgyver.js library includes a navigation extension by default. All `<a>` links in the HTML document are monitored. Tapping on a link opens the `href` target as a new layer (like when calling [`AG.GUI.openLayer`](topics/GUI/methods/openLayer.md)). The native back button appears on the new layer, and tapping on it closes the new layer (by programmatically calling `[`AG.GUI.popLayer`](topics/GUI/methods/popLayer.md)`). The closed layer's HTML page has a few seconds to perform any code before it is removed from the device's memory.

To open links in a without showing the navigation bar, you should add the `ag_should_hide_navigation_bar=1` parameter to your link:

```html
<a href="my_doc.html?ag_should_hide_navigation_bar=1">This link doesn't show the navigation bar</a>
```

## Callback functions

As is common in JavaScript, methods of the appgyver.js API take `successCallback` and `failureCallback` functions as parameters. They are resolved asynchronously in appgyver.js: the callback functions are called after the method has finished talking to the native layer (e.g. the navigation bar right button is correctly shown), enabling you to seamlessly weave native functionalities into your app. As the names imply, the `successCallback` function is called if the API call is successful and `failureCallback` is called if the API call fails.

**More on callbacks**

Each method's API documentation explains in more detail:
* The success and failure conditions of the API calls, i.e. what happens in the native layer.
* The type and contents of all callback parameters.

### AG.Deferred

As an alternative to providing callback functions as parameters to the method call, AppGyver provides an implementation of jQuery-style Deferred objects with [AG.Deferred](Deferred/Deferred.md). The supported methods return an `AG.Deferred` object.

## Supported platforms

The latest version of appgyver.js is currently supported by both the [iOS](http://itunes.apple.com/us/app/appgyver-preview/id479747411) and [Android](https://play.google.com/store/apps/details?id=com.appgyver.android) versions of the Preview client.

The Android Preview client is still an early release and the API implementation is limited, so please see the [Android support](support/android.md) page for a list of supported API calls.