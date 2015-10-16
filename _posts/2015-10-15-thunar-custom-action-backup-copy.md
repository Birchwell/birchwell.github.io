---
layout: post
title: Thunar Custom Actions - Backup Copy
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://pointpont.github.io/thunar_custom_action/video/ffmpeg/conversion/2015/06/08/thunar-custom-actions-tutorial-convert-video-to-avi.html).

This custom action will backup selected files.

* Name: Make Backup Copy
* Description: Backup the selected file.
* Command: `cp --backup=t %f %f.backup`

Under `Appears if selection contains` make sure everything is checked.
