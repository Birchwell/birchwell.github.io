---
layout: post
title: Thunar Custom Actions - Backup Copy
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-actions-tutorial-convert-video-to-avi/).

This custom action will backup selected files.

* Name: Make Backup Copy
* Description: Backup the selected file.
* Command: 

`cp --backup=t %f %f.backup`

Under `Appears if selection contains` make sure everything is checked.
