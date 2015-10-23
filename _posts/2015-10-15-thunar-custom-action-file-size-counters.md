---
layout: post
title: Thunar Custom Action - File Size Counters and Actual File Size for Linux
tags:
- thunar custom actions
- zenity
- filesize
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-actions-tutorial-convert-video-to-avi/).

##Counter

This custom action will display the size of each selected file/folder in a pop-up window. The program Zenity must be installed for this action to work.

![image](http://i.imgur.com/yvdoHyX.png)

* Name: Counter
* Description: Determine size of multiple files and folders.
* Command: 

`du -chs --apparent-size %N | zenity --text-info`

Under `Appears if selection contains` make sure everything is checked.

##Report ACTUAL file size for Thunar

The program Zenity must be installed for this action to work.

Thunar has a strange weakness when it comes to reporting file sizes.

>>Thunar is reporting the MiB of the file as the number of KiB/1000, which is the method that hard drive manufacturers use to dupe us into believing we're getting a larger hard drive than we actually get.  Read more about the problem [here](http://pclosmag.com/html/Issues/201307/page01.html).

This works on files, but YMMV on folders. It's supposed to work on folders, but the results are screwy.

![image](http://i.imgur.com/76KBJlX.png)

* Name: Actual File Size
* Description: Report the ACTUAL file size
* Command: 

`/home/$USER/Scripts/file-size.sh %N`

Under `Appears if selection contains` make sure everything is checked.

###Bash Script

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `file-size.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type `chmod +x file-size.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](https://gist.github.com/Birchwell/e1dcb5055cfea83b8f28)
