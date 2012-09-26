# AG.GUI.showNavigationBar

## Summary
`showNavigationBar()` shows the native navigation bar for the current view, with the title or title image given as a parameter.

## Quick example:
```javascript
AG.GUI.showNavigationBar("Front page");
```

## Syntax
```javascript
AG.GUI.showNavigationBar(title, titleImagePath)
```

**Parameters**

* *string* **title**<br>
  The title text shown on the navigation bar.
* *string* **titleImagePath**<br>
  A file path, pointing to an image to be shown on the navigation bar. The path is relative to the folder containing the Application folder, so an image in `MY_PROJECT/views/shared/navbar.png` will be accessible via the path `Application/shared/navbar.png`. Setting a `titleImagePath` overrides the `title` text.

## Returns
Nothing.

## Supported platforms
* iOS