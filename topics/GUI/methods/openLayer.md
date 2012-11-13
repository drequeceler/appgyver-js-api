# AG.GUI.openLayer

## Summary
`openLayer()` opens the target document in a new webview that exists as a separate layer on top of the original webview. The original webview remains active under the new layer. 

You can also define different animations and animation durations for opening and popping (closing) the layer.

By default, the new layer includes a native back button that will pop the layer and return to the webview under it. You can also use [AG.popLayer](popLayer.md) to pop the layer programmatically.

## Quick example:
```javascript
AG.GUI.openLayer("second_level/index.html", 
	{ 
		hidesNavigationBar: true,
		pushAnimation: "flipVerticalFromBottom",
		pushAnimationDuration: 1,
		popAnimation: "flipVerticalFromTop",
		popAnimationDuration: 1
	}
);
```

## Syntax
```javascript
AG.GUI.openLayer(location, options)
```

**Parameters**

* *string* **location**<br>
  The local URL pointing to the HTML document that will be opened on the new layer. Relative to the root of the `views` folder.
* *JSON* **options**
  A JSON object containing the options for the method call as key-value pairs:
	* *boolean* **hidesNavigationBar**
  	When set to `true`, the new layer opens without the native navigation bar. [`AG.GUI.popLayer`](popLayer.md) can then be used to close the layer.
  * *string* **pushAnimation**
		Determines the animation used to open the new layer. By default, the layer slides in from the right. Possible other values are:
		* "curlDown"
		* "curlUp"
		* "fade"
		* "flipVerticalFromBottom"
		* "flipVerticalFromTop"
		* "flipHorizontalFromLeft"
		* "flipHorizontalFromRight"
	* *double* **pushAnimationDuration**
	  Length of the push animation, in seconds (fractions are ok).
	* *string* **popAnimation**
	  Determines the animation used to pop the newly opened layer. By default, the layer slides out to the right. Possible other values are the same as in pushAnimation.
	* *double* **popAnimationDuration**
	  Length of the pop animation, in seconds (fractions are ok).

## Returns
Nothing.

## Supported platforms
* iOS