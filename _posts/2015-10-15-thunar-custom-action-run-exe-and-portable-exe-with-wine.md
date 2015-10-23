---
layout: post
title: Thunar Custom Action - Run Executable and Portable Executable with Wine
tags:
- thunar custom action
- .EXE files
- Wine
- portable programs
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-actions-tutorial-convert-video-to-avi/).

##Run .EXE program with Wine

* Name: Run with Wine
* Command: 

`wine %f`

Under `Appears if selection contains` make sure `Other Files` is checked. And type `*.exe` into the file pattern box.

##Run Specific Portable .EXE program with Wine

This is slightly different than the custom action above. Say you have a portable Irfanview and want to have a custom action which will open up a picture in it. Add the filepath to the portable program to the custom action command, preceded by “wine” and appended with “%f”.

* Name: Open with [Name of portable program]
* Description: Open [filetype] with [portable program]
* Command: 

`wine /home/$USER/portable.exe %f`

Under `Appears if selection contains` make sure `Image Files` is checked if you want to associate the command with an image program. If you want to associate the command with a video program or a text editor or WinRar, then you will have to check different boxes accordingly. Make sure the path to the file and the filename is correct in the command.
