---
layout: post
title: Copy Filename and Path
tags:
- thunar custom action
- xclip
category: posts
---

To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/tutorial-convert-video-to-avi/).

This action comes in handy when you need the full filepath for a file, e.g. when manipulating files through the terminal. The program `xclip` must be installed for this action to work.

* Name: Copy Filename and Path
* Description: Copy filename and path to the clipboard
* Command: 

`echo -n %f | xclip -selection c`

Under `Appears if selection contains` make sure everything is checked.
