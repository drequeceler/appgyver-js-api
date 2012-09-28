# AG.device

The **AG.device** namespace contains methods that give access to device-specific information, including the current contents of the screen.

## Methods

* [AG.device.takeScreenshot](methods/takeScreenshot.md)

## Full example ##

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
    document.addEventListener("DOMContentLoaded", function(){

      // device.takeScreenshot
      document.querySelector("#takeScreenshot").addEventListener("touchstart", function(){
        AG.device.takeScreenshot(
          // successCallback
          function(obj){
            var img = document.createElement("img");
            img.src = obj.screenshot;
            document.body.appendChild(img);
          },
          // failureCallback
          function(){
            navigator.notification.alert("Could not take screenshot");
          });
      });


    }, false);
    </script>
  </head>
  <body>
    <h1>AG.device examples</h1>
    <button id="takeScreenshot">Take screenshot</button>
  </body>
</html>
```