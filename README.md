# AudioPick
A *Chrome Extension* to pick a default audio output device for HTML5 audio and video elements

## How it works
The extension finds HTML5 audio and video elements within the document tree and manipulates the `sinkId` in order
to switch to the desired audio output device. The extension does not and will never find flash objects.
It also does not find audio/video node objects (`new Audio(...)`) that have not been inserted into the document tree.

**Note** that the API requires a successful call to `getUserMedia()` for every site with audio sinks that
need to be manipulated which - as a result - creates entries under `contentSettings['microphone']`, i. e.
it allows those sites to access your microphone.
