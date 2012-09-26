# AG.events

The **AG.events** namespace gives access to various event listeners that get fired when specific conditions are met. These event listeners are webview-specific, meaning that an event listener added to one webview won't get fired when the condition is met in another webview.

## Methods

* [AG.events.addEventListener](methods/addEventListener.md)
* [AG.events.removeAllEventListeners](methods/removeAllEventListeners.md)

## Full example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
        document.addEventListener("DOMContentLoaded", function(){          
          
          var buttons = document.querySelectorAll("button");;
          
          for (var i = 0; i < buttons.length; i++) {
            buttons[i].addEventListener("touchstart", function() {
              
              var lst = this.getAttribute("data-listener");
              
              if (lst != "removeAll") {  
                AG.events.addEventListener(lst, function () {
                  navigator.notification.alert(lst, false, "Event listener fired:");
                });
                navigator.notification.alert(lst, false, "Event listener added:");
                
              } else {                
                AG.events.removeAllEventListeners();
                navigator.notification.alert("All event listeners removed!");                
              }

            });
          }
        }, false);
    </script>
  </head>
  <body>
    <h1>AG.events example</h2>
      
    <button data-listener="focus">Add focus listener</button><br>
    <button data-listener="lostFocus">Add lostFocus listener</button><br>
    <br>
    <br>
    <button data-listener="removeAll">Remove all event listeners</button>
  </body>
</html>
```