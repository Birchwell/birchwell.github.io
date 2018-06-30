---
layout: post
title: Backup Copy
tags:
- thunar custom action
- backup
category: posts
---
To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/tutorial-convert-video-to-avi).


This custom action will backup selected files.

* Name: Make Backup Copy
* Description: Backup the selected file.
* Command: 

`cp --backup=t %f %f.backup`

Under `Appears if selection contains` make sure everything is checked.
