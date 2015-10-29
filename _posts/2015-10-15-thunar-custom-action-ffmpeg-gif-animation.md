---
layout: post
title: Thunar Custom Action - FFMPEG GIF Animation
tags:
- thunar custom action
- gif animation
- ffmpeg
- find
- sed
- xargs
category: posts
---
To learn how to use Thunar Custom Action click [here](https://birchwell.github.io/posts/thunar-custom-action-tutorial-convert-video-to-avi/).

This command produces a pretty good quality animated gif with a reasonably small footprint. The scale parameter will size the animated gif according to width, while retaining the correct aspect ratio. `-t 10` limits the output to 10 seconds. `-r 10` forces a frame rate of 10 frames per second. This command works best with versions of FFmpeg 2.0 and above. Check out the source link at the bottom of the post for additional ways to produce quality animated gifs, particularly LordNeckbeard’s answer. NOTE: Change the video format in the following commands and bash script to the format you're working with.

`ffmpeg -i input.avi -vf scale=520:-1 -t 10 -r 10 output.gif`

Example output (520×325, 920KB, 51 frames):

![GIF Animation (Galaxy Craze in Nadja) - Thunar Custom Action](http://i.imgur.com/tU7Vfmq.gif)

###Video to GIF

This custom action will work on 1 video file at a time.

* Name: Create Animated Gif
* Command: 

`xfce4-terminal -x ffmpeg -i %f -vf scale=320:-1 -t 10 -r 10 output.gif`

Under `Appearance conditions` check `Video Files`.

[Source](http://superuser.com/questions/556029/how-do-i-convert-a-video-to-gif-using-ffmpeg-with-reasonable-quality)

###Multiple Videos to Multiple GIFs

This bash script custom action will work on multiple video files, outputting multiple GIFs renamed with incremental numbering. It's useful in conjunction with the [Split Video custom action](https://birchwell.github.io/posts/thunar-custom-action-split-video/), by splitting a long video into 5 second clips and then converting select clips to GIF. NOTE: I can't get the bash script to only convert select videos. It will convert ALL videos in a folder to multiple GIFs, so be careful. Also the video file names must not contain spaces.

* Name: Multiple Videos to Multiple GIFs
* Description: Converts multiple videos to multiple GIFs
* Command: 

`/home/$USER/Scripts/videotogif.sh %N`

Under `Appearance conditions` check `Video Files`.

###Bash Script

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `videotogif.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type `chmod +x videotogif.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](https://gist.github.com/Birchwell/38a7e6f7e28e0cbd558f)

###Additional Command:

This command can be used as-is as a bash script.

~~~~~
find . -maxdepth 1 -name "*.mp4" -print0 |
  sed -z 's/\.mp4$//' |
  xargs -r0 -I FILENAME ffmpeg -i FILENAME.mp4 -vf scale=320:-1 -t 10 -r 10 
FILENAME.gif
~~~~~

[Source](https://unix.stackexchange.com/questions/174503/convert-multiple-videos-to-multiple-gifs)
