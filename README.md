# UwO_VideoPlayer_Extension_Release

**It is assumed that you have BepInEx 5.4.22 installed to use this.**

**All players must have this installed!**
## Installation
1. Put the `UnityEngine.VideoModule.dll` in the Dllstouse.
2. Put the `UwO_VideoPlayer_Extension.dll` in the plugins folder (Should be in `KoboldKare\BepInEx\plugins`).
3. Subscribe to my workshop mod for the actual video player screen: https://steamcommunity.com/sharedfiles/filedetails/?id=3430064473 (Remember to enable the mod)
## How to use
 **Only the host has the ability to control video players. So only the host can `Set URL`, Play, Pause etc.**

**The plugin can be enabled for public lobbies by putting `(V)` in the lobby name when creating/hosting it.**

1. Spawn in a video player using one of the following commands:
`/give uwoHugeVP`
`/give uwoBigVP`
`/give uwoMediumVP`
`/give uwoSmallVP`
2. Press the menu for showing video players (Default is F10).
3. Paste a direct link of the video you want to play into the URL text field and press the button `Set URL`.
4. The video player will auto play when it's ready.
## Video compatibility
You can't play YouTube videos directly and there's a lot of weird oddities with the video player. It will usually depend on the video/audio encoding, but some webm files will play while others will not. MP4 files are usually the way to go.

For shorter YouTube videos, I recommend using this site https://cnvmp3.com/v14, otherwise proceed to below:

The workaround to get pretty much any video to play is rather tedious, but so far has had a 100% success rate:
1. Download and install: https://sourceforge.net/projects/avisynth2/
2. Download and extract somewhere: https://github.com/argorar/WebMConverter/releases/download/3.42.0/WebMConverter-3.42.0.zip
3. Open the folder you just extracted and run `WebMConverter.exe`.
4. Paste in your video link (A YouTube link for example) and it'll ask for location on your hard drive, just close the window and it should start downloading.
5. Go to the `Encoding` tab in the program and tick the `Activate mp4 conversion` on under "Video". Ensure the encoding is H.264. Also tick `Enable audio` on under "Audio" if you want the video to play that as well.
6. Set an output location for your MP4 video and click the big `Convert` button in the top-right corner and it should start converting it to a playable format (unless you encounter an error).
7. Once it's done converting, upload it somewhere where you can get the direct link to the file. If you have Discord Nitro I recommend uploading it somewhere on Discord and copying the link to the video (right click on the video and click `Copy Link` at the bottom. You can now paste this link into the video player menu and it should play.
## Playing a video locally
It's possible to play videos directly from your hard drive, but for this to work in multiplayer, the video player plugin assumes the video file to have the exact same path as the host.

For example: `file:///C:/Not Porn/DefinitelySFWMovie.mp4`

There's not guarantee it'll play the video unless it's a compatible file type and has compatible encodings.
## For modders
If you'd like to make your own video player object that's compatible with my plugin you should make sure do the following for the object:

- Add a video player component
- Make sure `Source` is set to `URL`.

Anything other than that is up to you. I don't recommend setting `Audio Output Mode` to `Direct` since it'll play the videos audio straight into people's heads. Instead, add an audio source component and make sure the `Audio Source` field in the video player component is set to that audio component. I recommend playing around with the `3D Sound Settings` in the `Audio Source` component, like the `Volume Rolloff` graph. I will include my prefabs of my video players here for anyone who'd like to build upon them further.
