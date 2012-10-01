# ~~AG.media~~ (deprecated methods)

*The following methods are deprecated by the [Cordova APIs](http://docs.phonegap.com). Note that AG.media also contains [non-deprecated methods](../../../topics/media/media.md).*

The **AG.media** namespace contains methods that allow you to record and play back audio.

## Deprecated methods
* [AG.media.startRecordingAudio](methods/startRecordingAudio.md)
* [AG.media.stopRecordingAudio](methods/stopRecordingAudio.md)

## Full example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
    document.addEventListener("DOMContentLoaded", function() {
      
      var startRecord = function() {
        AG.media.startRecordingAudio("myaudio");        
      }
      
      var stopRecord = function() {
        AG.media.stopRecordingAudio();
      }
      
      var play = function() {
        AG.media.play("myaudio");
      }
      
      document.querySelector("button#start_record").addEventListener("touchstart", startRecord);
      document.querySelector("button#stop_record").addEventListener("touchstart", stopRecord);
      
    });
    </script>
  </head>
  <body>
    <h1>AG.media example</h1>
    <button id="start_record">Start recording</button>
    <button id="stop_record">Stop recording</button>
 
  </body>
</html>
```