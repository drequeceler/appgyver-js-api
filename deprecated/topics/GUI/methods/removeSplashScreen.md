# ~~AG.GUI.removeSplashScreen~~ (deprecated)

*This method is deprecated and only available in Legacy mode.*

## Summary
`removeSplashScreen()` can be used to remove the native splash screen that is shown when the application is loading. This can be useful if your application needs to wait for some assets to load, for example.

## Quick example:
```javascript
AG.GUI.removeSplashScreen("fade");
```

## Syntax
```javascript
AG.GUI.setTopBarImagePath(effect)
```

**Parameters**

* *string* **effect**<br>
  The name of the effect used to remove the splash screen. Possible values are:
    * `fade`
    * `slideFromLeft`
    * `slideFromRight`

## Returns
Nothing.

## Supported platforms
* iOS (Legacy mode only)