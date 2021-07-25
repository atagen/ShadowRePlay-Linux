# ShadowRePlay

  

Recreates Shadowplay's replay feature on Linux

  

- compatible with Nvidia (nvenc), AMD (vaapi,amf/vce), Intel (quicksync) GPUs, as well as libx264.

  

## Prerequisites

 

- Have FFMPEG, libnotify, and xdotool installed

-  `sudo pacman -S ffmpeg libnotify xdotool` (installer will do this if need be)


- Have one of (in order of priority given):
    * i3
    * sxhkd
    * Xbindkeys


 

## Installation

You can get the old version on AUR as `shadowreplay-git`.

Otherwise, shadowreplay can be installed by running the `install` file after cloning this repo.

This will install the required dependencies on Arch.
  

## Configuration


Variables specific to your desired setup can be found in the example_config which is installed to `$HOME/.config/shadowreplay`

These will take precedence over any you see defined in the script.


## Setup

  

### Keybind Setup

i3/sxhkd/Xbindkeys presence should be detected and autobound.

- Meta+F9 to start, Meta+F10 to close, F9 to capture.

If for some reason they are not bound correctly or you wish to rebind them, please refer to the appropriate configuration file for your keybind program.

The commands to bind are as follows:

- To start: `notify-send ShadowRePlay Running..;shadowreplay`                                                
- To stop: `notify-send ShadowRePlay Stopping.;killall shadowreplay & killall -s1 ffmpeg`                    
- To capture: `"""killall --user "$USER" --ignore-case -signal SIGTERM ffmpeg"""` 


  

### Usage

  

- (Preferred) hit key combo to start shadowplay. (Otherwise) run `shadowreplay` in a terminal

- Press your configured hotkey to save the replay.

  

## TODO

- More flexible audio input support

- Ability to downscale video output during recording

- Dynamic video buffer size allocation based on resolution and FPS
  

## Notes

Thank you [MAPReiff](https://github.com/MAPReiff) for the original script. 

Heavily inspired by [Toqozz's script](https://github.com/Toqozz/shadowplay-linux).

Thank you [Tyler](https://github.com/durcor) for fielding MAPReiff's questions while making this.
