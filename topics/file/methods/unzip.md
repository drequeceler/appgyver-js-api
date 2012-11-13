# AG.file.unzip

## Summary
`unzip()` unzips a .zip file in your app's filesystem in the background.

The success callback function gets triggered after the file has been successfully unzipped. If the unzipping fails, the failure callback function gets triggered.

## Quick example:
```javascript
AG.file.unzip("Application/assets/stuff.zip", "Application/unzip_here/", function(){
  navigator.notification.alert("File was unzipped successfully!");
});
```

## Syntax
```javascript
AG.file.unzip(filenameWithPath, toPath, successCallback, failureCallback)
```

**Parameters**

* *string* **filenameWithPath**<br>
  A string containing the filename and path of the file to be unzipped. The path is relative to the `Documents` directory on your device. Thus, a file located at `MY_PROJECT/views/myzip.zip` on your disk will be accessible via the path `Application/myzip.zip` (the contents of the `views` folder are copied to the `Application` folder on the mobile device).
* *string* **toPath**<br>
  A string containing the path where the file will be unzipped. The path is relative to the `Documents` directory on your device.
* *function* **successCallback**<br>
  The success callback function.
* *function* **failureCallback**<br>
  The failure callback function.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS, Android

