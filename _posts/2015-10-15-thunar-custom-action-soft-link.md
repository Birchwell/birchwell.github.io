---
layout: post
title: Thunar Custom Actions - Create Soft Link
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://pointpont.github.io/thunar_custom_action/video/ffmpeg/conversion/2015/06/08/thunar-custom-actions-tutorial-convert-video-to-avi.html).

Create a soft link to a folder or file. This is the same as a symbolic link, but the command is somewhat different from the SymLink custom action that comes default with Thunar.

* Name: Create Soft Link
* Description: Create a soft link to a folder or file
* Command: `ln -s %f $(zenity --file-selection --directory)`

Under `Appears if selection contains` make sure everything is checked.
