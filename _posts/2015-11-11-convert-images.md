---
layout: post
title: Convert Images
tags:
- thunar custom action
- convert
- graphics
- zenity
category: posts
---
To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/tutorial-convert-video-to-avi).

Convert the selected files to the user defined graphic format (jpg, png, tiff, webp, gif, etc). Quality can be set. The converted images will be placed in a separate folder and the originals will remain intact. Zenity must be installed.

* Name: Convert Images
* Description: Convert the selected files to the user defined graphic format
* Command: 

`/home/$USER/Scripts/convert-image.sh %N`

Under `Appears if selection contains` make sure `Image Files` is checked.

Change `/home/$USER/Scripts/convert-image.sh` to the path of the bash script, and change `convert-image.sh` to the name you give the bash script.

###Bash Script:

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script: `convert-image.sh`. Save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type: `chmod +x convert-image.sh` And press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](http://gist.github.com/Birchwell/3311a9d63c21ca24d021)
