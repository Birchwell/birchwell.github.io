---
layout: post
title: Extract Audio from Video
tags:
- thunar custom action
- ffmpeg
- audio
- editing
category: posts
---
To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/tutorial-convert-video-to-avi).

##Extract Audio from Video

This custom action will extract audio from video and save the audio in the working folder. The program FFmpeg must be installed for this action to work.

* Name: Extract audio
* Description: Extract audio from video
* Command: 

`ffmpeg -i %f -vn -ar 44100 -ac 2 -ab 192 -f mp3 output.mp3`

Under `Appears if selection contains` make sure only `Video Files` is checked.
