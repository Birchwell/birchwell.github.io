---
layout: post
title: Thunar Custom Action - Convert Video to Multiple Formats
tags:
- thunar custom actions
- zenity
- video
- ffmpeg
- convert
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-action-tutorial-convert-video-to-avi/).

This command works with a bash script (below). Convert video to avi, 3gp, flv, mov, mp4, asf, wmv, mkv, mpg. The video and audio bitrates can be set.

* Name: Convert Video
* Description: Convert from one format to another.
* Command: 

`/home/$USER/Scripts/convertvideo.sh %n`

Under `Appears if selection contains` make sure `Video Files` is checked.

###Bash Script

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `convertvideo.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type chmod +x `convertvideo.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](https://gist.github.com/Birchwell/94549e064a6499a490c4)
