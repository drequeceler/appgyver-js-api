# AG.camera.flashToggle

## Summary
`flashToggle()` switches the flash LED of the device's camera on if it is off, and vice versa.

The success callback function is triggered if the flash LED is successfully turned on or off.

The failure callback function is triggered if the device does not have a camera flash LED.

## Quick example:
```javascript
AG.camera.flashToggle();
```

## Syntax
```javascript
AG.camera.flashToggle(successCallback, failureCallback)
```

**Parameters**

* *function* **successCallback**<br>
  Success callback function.
* *function* **failureCallback**<br>
  Failure callback function.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS