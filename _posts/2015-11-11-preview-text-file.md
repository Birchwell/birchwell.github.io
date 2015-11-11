---
layout: post
title: Preview Text File
tags:
- thunar custom action
- zenity
- text
category: posts
---
To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/convert-video-to-avi/).

This command will preview a text file in a Zenity pop-up box. Decrease or increase `300` in the command to change the amount of text that is previewed. Zenity must be installed.

* Name: Preview Text File
* Description: Preview the selected text file
* Command: 

`head -n 300 %f | zenity --text-info --width=450 --height=400 --title="Text Preview"`

Under `Appears if selection contains` make sure `Text Files` is checked.
