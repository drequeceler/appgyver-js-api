# AG.GUI.showNavigationBar

## Summary
`showNavigationBar()` shows the native navigation bar for the current view, with the title or title image given as a parameter.

## Quick example:
```javascript
AG.GUI.showNavigationBar({title: "Front page"});
```

## Syntax
```javascript
AG.GUI.showNavigationBar(options)
```

**Parameters**

* *JSON* **options**<br>
  Array of key-value pairs, with the following keys:
  * *string* **title**<br>
    The text to be shown on the navigation bar.
  * *string* **titleImagePath**<br>
    A file path, pointing to an image to be shown on the navigation bar. The path is relative to the `Documents` folder on your mobile device, so an image in `MY_PROJECT/views/img/navbar.png` on your disk will be accessible via the path `Application/img/navbar.png` (the contents of the `views` folder are copied to the `Application` folder on the mobile device). Setting a `titleImagePath` overrides the `title` text.

## Returns
Nothing.

## Supported platforms
* iOS