# AG.events.addEventListener

## Summary
`reloadStartURL()` resets the current webview to whatever URL it was initially loaded with. If the document `index.html` was opened to a webview via the  [AG.GUI.openLayer](openLayer.md) API call or via a tab bar button, and then `window.location` gets changed to another document, e.g. `show.html`, then calling `reloadStartURL()` reloads the webview with `index.html`.


## Quick example:
```javascript
AG.GUI.reloadStartURL();
```

## Syntax
```javascript
AG.GUI.reloadStartURL()
```

**Parameters**

No parameters.

## Returns

Nothing.

## Supported platforms
* iOS