# AG.media

The **AG.media** namespace contains methods that allow you to play back audio.

## Deprecated methods
* [AG.media.play](methods/play.md)

## Full example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
    document.addEventListener("DOMContentLoaded", function() {
            
      var play = function() {
        AG.media.play("Application/shared/myaudio.wav");
      }
      
      document.querySelector("button#play").addEventListener("touchstart", play);
      
    });
    </script>
  </head>
  <body>
    <h1>AG.media example</h1>
    <button id="play">Play</button>
 
  </body>
</html>
```