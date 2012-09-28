# AG.media.play

## Summary
`play()` plays an audio file from the app's file system. Supported formats include .aiff, .mp3, .ogg and .wav.

Note that playing .mp3 files has a slight delay compared to .wav files due to the decoding process.

*There is currently a known issue where playing a nonexistent audio file crashes the app.*

## Quick example:
```javascript
AG.media.play("Application/www/audio/myaudio.wav");
```

## Syntax
```javascript
AG.media.play(filename)
```

**Parameters**

* *string* **filename**<br>
  The filename and path of the audio file to play. The path is relative to the `Documents` directory on the phone. Thus, a file located at `MY_PROJECT/www/audio/myaudio.wav` on your disk will be accessible via the path `Application/www/audio/myaudio.wav`.

## Returns
Nothing.

## Supported platforms
* iOS