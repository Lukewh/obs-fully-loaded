<h1 align="center">
  <img src="https://avatars1.githubusercontent.com/u/7725691?v=3&s=256" alt="OBS Studio">
  <br />
  OBS Studio - <i>Fully Loaded!</i>
</h1>

<p align="center"><b>This is an install script for OBS Studio</b>, <i>"Free and open source software for live streaming and screen recording; that comes pre-loaded with extra features and plugins!"</i> It works on Ubuntu and derivative distributions.
<br />
Made with 💝 for <img src=".github/ubuntu.png" align="top" width="18" /></p>

## Install

```bash
git clone https://github.com/wimpysworld/obs-fully-loaded.git
cd obs-fully-loaded
sudo ./obs-install.sh
```

# Batteries included

This script install OBS Studio from the official PPA and then install a collections of 3rd party
plugins and themes.

  * Supports **nvenc (NVIDIA) and VA-API (AMD & Intel) accelerated video encoding**.
  * **[Advanced Scene Switcher](https://github.com/WarmUpTill/SceneSwitcher)** plugin; an automated scene switcher.
  * **[Audio Pan](https://github.com/norihiro/obs-audio-pan-filter)** plugin; control stereo pan of audio source.
  * **[Browser](https://github.com/obsproject/obs-browser)** plugin; CEF-based OBS Studio browser plugin.
  * **[Directory Watch Media](https://github.com/exeldro/obs-dir-watch-media)** plugin; filter you can add to media source to load the oldest or newest file in a directory.
  * **[DVD Screensaver](https://github.com/univrsal/dvds3)** plugin; a DVD screen saver source type.
  * **[Downstream Keyer](https://github.com/exeldro/obs-downstream-keyer)** plugin; add a Downstream Keyer dock.
  * **[Dynamic Delay](https://github.com/exeldro/obs-dynamic-delay)** plugin; filter for dynamic delaying a video source.
  * **[Freeze Filter](https://github.com/exeldro/obs-freeze-filter)** plugin; freeze a source using a filter.
  * **[Gradient Source](https://github.com/exeldro/obs-gradient-source)** plugin; adding gradients as a Soource.
  * **[GStreamer](https://github.com/fzwoch/obs-gstreamer)** plugins; feed GStreamer launch pipelines into OBS Studio and use GStreamer encoder elements.
  * **[Move Transition](https://github.com/exeldro/obs-move-transition)** plugin; move source to a new position during scene transition.
  * **[NDI](https://github.com/Palakis/obs-ndi)** plugin; Network A/V via NewTek's NDI.
  * **[NvFBC](https://gitlab.com/fzwoch/obs-nvfbc)** plugin; screen capture via NVIDIA FBC API. Requires [NvFBC patches for Nvidia drivers](https://github.com/keylase/nvidia-patch) for consumer grade GPUs.
  * **[Recursion Effect](https://github.com/exeldro/obs-recursion-effect)** plugin; recursion effect filter.
  * **[Replay Source](https://github.com/exeldro/obs-replay-source)** plugin; slow motion replay async sources from memory.
  * **[RGB Levels](https://github.com/petrifiedpenguin/obs-rgb-levels-filter)** plugin; simple filter to adjust RGB levels.
  * **[RTSPServer](https://github.com/iamscottxu/obs-rtspserver/)** plugin; encode and publish to a RTSP stream.
  * **[Source Copy](https://github.com/exeldro/obs-source-copy)** plugin; adds copy and paste options to the tools menu.
  * **[Source Record](https://github.com/exeldro/obs-source-record)** plugin; make sources available to record via a filter.
  * **[Source Switcher](https://github.com/exeldro/obs-source-switcher)** plugin; to switch between a list of sources.
  * **[Spectralizer](https://github.com/univrsal/spectralizer)** plugin; audio visualization using fftw.
  * **[StreamFX](https://github.com/Xaymar/obs-StreamFX)** plugin; collection modern effects filters and transitions.
  * **[Text Pango](https://github.com/kkartaltepe/obs-text-pango)** plugin; Provides a text source rendered using Pango with multi-language support, emoji support, vertical rendering and RTL support.
  * **[Text PThread](https://github.com/norihiro/obs-text-pthread)** plugin; Rich text source plugin with many advanced features.
  * **[Time Warp Scan](https://github.com/exeldro/obs-time-warp-scan)** plugin; a time warp scan filter.
  * **[Transition Table](https://github.com/exeldro/obs-transition-table)** plugin; customize scene transitions.
  * **[VNC Source](https://github.com/norihiro/obs-vnc)** plugin; VNC viewer that works as a source.
  * **[Websockets](https://github.com/Palakis/obs-websocket)** plugin; remote-control OBS Studio through WebSockets, compatible with [StreamControl](https://play.google.com/store/apps/details?id=dev.t4ils.obs_remote&hl=en).

## OBS Virtual Camera

Starting with OBS Studio 26.1, Virtual Camera support is integrated. The
`Start Virtual Camera` button is located in the Controls pane, just below
`Start Recording`.

Here's how to install and configure `v4l2loopback` which OBS uses:

```
sudo snap connect obs-studio:kernel-module-observe
sudo apt -y install v4l2loopback-dkms v4l2loopback-utils
echo 'options v4l2loopback devices=1 video_nr=13 card_label="OBS Virtual Camera" exclusive_caps=1' | sudo tee /etc/modprobe.d/v4l2loopback.conf
echo "v4l2loopback" | sudo tee /etc/modules-load.d/v4l2loopback.conf
sudo modprobe -r v4l2loopback
sudo modprobe v4l2loopback devices=1 video_nr=13 card_label="OBS Virtual Camera" exclusive_caps=1
```

**NOTE!** Using `video_nr` greater than 64 will not work.

## Additional plugins

If this install script doesn't include a plugin that you use, you can a download
pre-compiled plugin and and extract it to `~/.config/obs-studio/plugins/`.
