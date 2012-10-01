# AG.media.play

The `AG.media.play` API is provided as an alternative to Cordova's `media.play` API. It provides a simple, one-line playback of an audio file. The playback is concurrent and polyphonic, meaning you can play multiple sounds simultaneously, as well as multiple instances of the same sound on top of each other. (Cordova's current `media.play` API is not polyphonic.)

## Summary
`play()` plays an audio file from the app's file system. Supported formats include .aiff, .mp3, .ogg and .wav.

Note that playing .mp3 and .ogg files has a slight delay compared to .wav files due to the decoding process.

## Quick example:
```javascript
AG.media.play("Application/shared/audio/myaudio.wav");
```

## Syntax
```javascript
AG.media.play(filename)
```

**Parameters**

* *string* **filename**<br>
  The filename and path of the audio file to play. The path is relative to the `Documents` directory on the phone. Thus, a file located at `MY_PROJECT/views/shared/audio/myaudio.wav` on your disk will be accessible via the path `Application/shared/audio/myaudio.wav` (the `views` folder is removed when the app is downloaded onto the mobile device's file system).

## Returns
Nothing.

## Supported platforms
* iOS