---
layout: post
title: Thunar Custom Action - Watermark Images
tags:
- thunar custom action
- graphics
- editing
category: posts
---
![image](http://i.imgur.com/0PPOfuI.jpg)

To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-actions-tutorial-convert-video-to-avi/).

This custom action works with a bash script (below). Images will be watermarked after entering custom text into a dialog box and pressing enter. The originals will be copied to a subfolder of the working directory named backups. Edit the script to modify the default watermark settings to your liking.

* Name: Watermark
* Description: Watermark images.
* Command: 

`/$USER/Scripts/watermark.sh %N`

Change `$USER/Scripts/watermark.sh` to the path of the bash script (Copy Filename and Path Custom Action above can be used for this!), and change `watermark.sh` to the name you give the bash script. Under `Appears if selection contains` make sure `Image Files` is checked.

###Creating Bash Script:

I keep my bash scripts in a folder named Scripts in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `watermark.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type `chmod +x watermark.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions. To learn more about Thunar Custom actions click here.

[Bash Script](https://gist.github.com/Birchwell/4c675025e91d0c70b129)
