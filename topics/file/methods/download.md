# AG.file.download

## Summary
`download()` download a remote file to your application's directory.

The success callback function gets triggered if the file download is successful. If not, the failure callback function gets triggered. The recurring callback function gets triggered as the download progresses.

## Quick example:
```javascript
AG.file.download("Files/kernel.iso", "http://mirror.sov.uk.goscomb.net/ubuntu-releases/precise/ubuntu-12.04.1-desktop-i386.iso", function(){
    navigator.notification.alert("File was downloaded!");
  }, null, function(parameters) {
    downloadSize.innerHTML = parameters.size;
    downloadDownloaded.innerHTML = parameters.downloaded;
    downloadRate.innerHTML = parameters.rate;
  });
```

## Syntax
```javascript
AG.file.download(toFile, url, successCallback, failureCallback, recurringCallback(parameters))
```

**Parameters**

* *string* **toFile**<br>
  A string containing the filename and path where the downloaded file will be saved. The path is relative to the app's `views` directory.
* *string* **url**<br>
  The remote URL where the file will be downloaded from
* *function* **successCallback**<br>
  The success callback function, called when the file is fully downloaded.
* *function* **failureCallback**<br>
  The failure callback function.
* *function* **recurringCallback**<br>
	A recurring callback function that provides data abut the size, amount downloaded and download rate of the download. The callback parameter is an object with the following fields:
	* *object* **parameters**
		* *string* **size** <br>
	  	Size of the file downloading, in bytes.
		* *string* **downloaded**<br>
	  	Bytes of the file downloaded.
		* *string* **rate**<br>
			Current rate of the download, in bytes/sec.


## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS, Android (recurring callback not supported)

