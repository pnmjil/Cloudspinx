## Media Players / Video Editors

Media players are hardware or software devices used to play multimedia files e.g audio files, video files, image files and digital media files. These tools play files stored on a storage device, on a disc or streamed from the internet. 

Media players support various file formats e.g MP3, WAV, AVI,MP4 and many more with the ability to organise media files into music, videos and photos. This helps you to sort your files in your playlist. Media players allows the user to playback and control the progress of their file by starting, pausing, stopping, volume adjustment, fast fowarding, playbacks, subtitles etc.

Video Editors are software programs that transforms raw video footage into an organised story. Video editors helps you to crop, trim or split your video into small clips, adding enhancements etc and then allows you to download your editied video as an MP4 to save and share with others. Video editors also allow the user to remove unwanted background noise from scenes and upload their preffered music to the video. A good video editor should have the ability to add feel and animated effects to the editted video.

If you intend to create promotional, youtube tutorials, stories and educational videos, then you need to learn how to edit the videos as most often, you will need to trim your videos as well as adding effects to your videos.

This documentation will major around common media players and how to install them in Ubuntu Desktop and its derivatives.

### 1. MPV Media Player

MPV Media Player is completely free open source software that is cross-platform in nature for the command line. Its preffered by many users because of its ability to support a wide range of media file formats, audio, video codecs and subtitle types. It has powerful scripting capabilities which makes the player a Swiss amy knife as it can do almost anything.

MPV media player is based on OpenGL, Vulkan and D3D11 for high quality video output e.g color management, frame timing, interpolation, HDR. It is built in C programming language which makes it highly embeddable and easily integratable into other applications. 

MPV is purely commandline based but provides an On Screen Controller on top of the video for basic control. MPV leverages most hardware decoding APIs on all platforms its installed on.

MPV media player is based on MPlayer and mplayer2 and has special input URL types available to read input from several sources. It has a fully configurable command-driven control layer to allow the user to control MPV using the keyboard, mouse or remote control.

#### Features

As seen on the brief introduction, its sufficient to note that MPV Media Player is rich in features as summarised below.

- MPV media player is free and open source.

- Supports multiple video file formats, audio and video codecs.

- It is cross-platform in nature.

- The user can take screenshots using the screenshot input mode command on a currently played file. The default **S** takes screenshots without subtitles while **s** includes subtitles.

- MPV has a terminal status line that shows the playback status on the terminal. e.g V for video and A for audio, current time position, total file duration, playback speed, playback percentage, encoding state,  display sync state, dropped frames and cache state.

- MPV Media Player has the ability to reduce latency by disabling features which increase latency because it is optimized for normal video playback.

- MPV Media Player has the ability to store a playback of a currently playing file and resume to it the next time that file is played.

- MPV Media Player supports many network protocols but the protocol prefix must always be specified e.g HTTP, HTTPS, ytdl, smb, etc

- MPV Media Player has no official GUI but has the On Screen Controller which acts as pseudo GUI mode for minimal control over keyboard, mouse or remote control.

- Supports multiple audio output drivers e.g pulse, openal, audiounit for iOS, pipewire, sdl, wasapi etc.

- Supports multiple video output drivers e.g gpu, xv, direct3d, sdl etc

- Supports multiple audio filters that allows the user to modify the audio stream and its properties e.g lavcac3enc, tempo, pitch etc

- MVP Media Player also supports multiple video filters to help the user to modify the video stream and its properties e.g --vf, colormatrix etc

- Supports many encoding formats and codecs making it easy to encode files from one format/codec to another.

- MPV Media Player is controlled with commands and properties and the user can interact with the player using key bindings, OSD, JSON IPC, client API and the classic slave mode.

For more details on this amazing Media Player, please visit the [MPV Manual](https://mpv.io/manual/master/).

#### Installation and Usage

To install MPV Media Player on Ubuntu Desktop, do the following.
