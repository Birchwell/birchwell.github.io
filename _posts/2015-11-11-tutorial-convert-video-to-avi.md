---
layout: post
title: Convert Video to AVI
tags:
- thunar custom action
- tutorial
- convert
- video
- ffmpeg
- backup
category: posts
---

Thunar is a file manager for Linux systems that comes packaged with the XFCE desktop environment. One of the main attractions of Thunar is the ability to add some very convenient and time saving customized actions by way of the Custom Actions utility inside Thunar.

![Thunar Custom Action Tutorial](http://i.imgur.com/N4eCel8.jpg)

I'll do a walkthrough tutorial with the following Custom Action.

###Convert video to AVI

This converting action requires that FFmpeg be installed, since it’s employed to convert the videos. This custom action will allow any video file to be converted to AVI.

* Open `Thunar`.
* Go to `Edit>Configure` custom actions. The Custom Actions window will appear.
* Add a new custom action by clicking the plus sign at the top right of the window.
* In the basic input box, type any descriptor. I type Convert to AVI. This is the text that will appear in the right-click context menu.
* In the description input box, type any descriptor. I type Convert any video to AVI.
* Add an icon, if desired, by clicking the no icon button. The icon will appear next to the action in the right-click context menu.
* In the command input box type:

`xfce4-terminal -x ffmpeg -i %f -b 798k -ab 128k %f.avi`

`xfce4-terminal -x` is a useful addition to the FFmpeg command, in that the terminal will appear when running the Custom Action, so that the progress of the conversion can be visually monitored.

The variables above, such as 798k video bitrate and 128k audio bitrate, can be changed to your quality preference.

* Click the `Appearance Conditions` tab at the top of the Create Action window. The file pattern input box should have an asterisk. Leave it alone. If it’s not there, enter it.
* Under `Appears if selection contains` make sure only the `Video Files` option is checked. When right-clicking on non-video files the custom action will not appear in the right-click context menu.
* Click OK.
* Close the Custom Actions window.
* Shut down all instances of Thunar and restart Thunar. (This is what I've heard from others, but I find the new Custom Action works even if you don't shutdown and restart Thunar.)

Now to test if it’s working. Open Thunar and find a small non-AVI video file. Right-click on the file. Convert to AVI will appear near the bottom of the right-click context menu. Click Convert to AVI. The terminal will appear and show ffmpeg doing its magic. The video will be converted to AVI, after which the terminal will automatically close. The converted output will be automatically saved to the directory of the converted video.

The steps for creating other Custom Actions are roughly the same as above, though different Custom Actions will have different commands and will work on different types of files.

###Backup Custom Actions

After a while you may have dozens of custom actions. Back them up so you don’t have to tediously re-enter them if something happens to your system, or if you install another system.

* Go to your personal $USER folder and hit CTRL-H to show hidden files. 
* Go to `/home/$USER/.config/Thunar/`. 
* In the Thunar folder copy the `uca.xml` file and paste it somewhere to back it up.
