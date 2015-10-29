---
layout: post
title: Thunar Custom Action - Show Media Data
tags:
- thunar custom action
- ffmpeg
- zenity
category: posts
---
To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/thunar-custom-action-tutorial-convert-video-to-avi/).

This custom action is similar to the popular program [Mediainfo](https://mediaarea.net/en/MediaInfo); it will show some basic specifications of any audio/video file. Though it’s best suited to audio/video files, it can identify image resolutions. Zenity must be installed to see the display.

![Media Data - Thunar Custom Action](http://i.imgur.com/hesELv5l.jpg)

* Name: Media Data
* Description: Find audio/video information.
* Command: 

`ffmpeg -i %f  2>&1 | grep -e Stream -e Duration -e Input | zenity --width=800 --height=240 --text-info --title %n`

Under `Appears if selection contains` make sure `Audio Files` and `Video Files` (and `Image Files` if wanted) is checked.
