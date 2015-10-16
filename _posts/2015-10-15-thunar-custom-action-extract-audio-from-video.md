---
layout: post
title: Thunar Custom Action - Extract Audio from Video
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://pointpont.github.io/thunar_custom_action/video/ffmpeg/conversion/2015/06/08/thunar-custom-actions-tutorial-convert-video-to-avi.html).

##Extract Audio from Video

This custom action will extract audio from video and save the audio in the working folder. The program FFmpeg must be installed for this action to work.

* Name: Extract audio
* Description: Extract audio from video
* Command: `ffmpeg -i %f -vn -ar 44100 -ac 2 -ab 192 -f mp3 output.mp3`

Under `Appears if selection contains` make sure only `Video Files` is checked.
