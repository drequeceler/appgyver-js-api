# AG.GUI.openLayer

## Summary
`openLayer()` opens the target document in a new webview that exists as a separate layer on top of the original webview. The original webview remains active under the new layer.

By default, the new layer includes a native back button that will close the layer and return to the webview under it.

## Quick example:
```javascript
AG.GUI.openLayer("second_level/index.html", { hidesNavigationBar: true });
```

## Syntax
```javascript
AG.GUI.openLayer(location, options)
```

**Parameters**

* *string* **location**<br>
  The local URL pointing to the HTML document that will be opened on the new layer.
* *JSON* **options**
  A JSON object containing the options for the method call as key-value pairs:
	* *boolean* **hidesNavigationBar**
  	When set to `true`, the new layer opens without the native navigation bar. [`AG.GUI.popLayer`](popLayer.md) can then be used to close the layer.

## Returns
Nothing.

## Supported platforms
* iOS (not in Legacy mode)