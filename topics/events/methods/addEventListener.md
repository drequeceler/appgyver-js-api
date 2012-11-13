# AG.events.addEventListener

## Summary
`addEventListener()` adds an event listener to the current webview that listens for the specified event. The available events are:

* **focus**<br>
 Happens when the current webview gains focus (after returning from another webview or after going to home screen and back).
* **lostFocus** / **unfocus**<br>
 Happens when navigation bar's native back button is tapped. The two event names perform identical events.

The success callback function of the event listener is fired every time the listened event happens.

## Quick example:
```javascript
AG.events.addEventListener("topDoubleTapped", function(){
  AG.GUI.alert("Success", "Top bar was double tapped!");
});
```

## Syntax
```javascript
AG.events.addEventListener(event, successCallback)
```

**Parameters**

* *string* **event**<br>
  The event that the event listener listens to. Possible values are:
    * `"focus"`
    * `"lostFocus"` / `"unfocus"`
 
    See above for more details on when the different events are triggered.
    
* *function* **successCallback**<br>
  The success callback function.

## Returns

Nothing.

## Supported platforms
* iOS, Android