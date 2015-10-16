---
layout: post
title: Thunar Custom Action - Show Media Data
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://pointpont.github.io/thunar_custom_action/video/ffmpeg/conversion/2015/06/08/thunar-custom-actions-tutorial-convert-video-to-avi.html).

This custom action is similar to the popular program [Mediainfo](https://mediaarea.net/en/MediaInfo); it will show some basic specifications of any audio/video file. Though it’s best suited to audio/video files, it can identify image resolutions. Zenity must be installed to see the display.

![image](http://i.imgur.com/hesELv5l.jpg)

* Name: Media Data
* Description: Find audio/video information.
* Command: `ffmpeg -i %f  2>&1 | grep -e Stream -e Duration -e Input | zenity --width=800 --height=240 --text-info --title %n`

Under `Appears if selection contains` make sure `Audio Files` and `Video Files` (and `Image Files` if wanted) is checked.
