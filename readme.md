# Local Jitsi Recording and getDisplayMedia experiments

Modified by [au2001](https://github.com/au2001).
See the webrtcHacks [post](https://webrtchacks.com/jitsi-recording-getdisplaymedia-audio) for full details.

## Local Jitsi Meet Recording

Quick hack to record your self hosted [Jitsi Meet](https://github.com/jitsi/jitsi-meet) session locally, just using your browser. Uses `getDisplayMedia` to capture user selected screen and `getUserMedia` for local audio.
Makes sure to click "Capture Audio" if you are using Chrome (or a Chromium-based navigator such as Microsoft Edge) to capture the remote participant sound via the system audio.

## Installation

```
git clone https://github.com/au2001/jitsiLocalRecorder.git
cd jitsiLocalRecorder
./install.sh
```

Installation assumes Jitsi Meet's web files are located in `/usr/share/jitsi-meet/index.html`.
If your files are located somewhere else, then run `./install.sh {{meet_web_dir}}` with the correct directory.

## Usage

Navigate to your Jitsi Meet website and join a room (e.g. [meet.example.com/test-room](https://meet.example.com/test-room)).

To show the controls, add "#record" at the end of the URL (e.g. [meet.example.com/test-room#record](https://meet.example.com/test-room#record)).
At the top left of your screen, you can start the recording by pressing Record.

To hide the controls (during the recording for example), remove "#record" but keep "#" at the end of the URL so that the webpage doesn't refresh (e.g. [meet.example.com/test-room#](https://meet.example.com/test-room#)).
The recording continues while the controls are hidden.
When you want to stop or pause it, insert again "#record" and click Stop/Pause.

After stopping the recording, press Play to preview the video. Press Save to download it locally as a [WebM](https://www.webmproject.org) file.

## getDisplayMedia testing

Load `getDisplayMedia.html` to:
 1. Check if your browser supports `getDisplayMedia` (it should)
 1. Demonstrate how getDisplayMedia ignores user constraints
 1. Check if you can capture audio (currently only Chrome for some user selections)
