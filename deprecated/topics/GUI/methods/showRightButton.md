# ~~AG.GUI.showRightButton~~ (deprecated)

## Summary
`showRightButton()` shows the native top right button in the navigation bar.

The recurring callback function is triggered when the button is tapped.

This method works only in normal mode.

## Quick example:
```javascript
var hello = function() { navigatior.notification.alert("I am an alert box", false, "Hello!") }

AG.GUI.showRightButton("Say hello", hello);
```

## Syntax
```javascript
AG.GUI.showRightButton(title, recurringCallback)
```

**Parameters**

* *string* **title**<br>
  The text shown on the button.
* *function* **recurringCallback**<br>
  A function that gets called every time the button is tapped.

## Returns
Nothing.

## Supported platforms
* iOS