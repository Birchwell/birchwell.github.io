---
layout: post
title: Thunar Custom Action - Upload to Imgur
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-actions-tutorial-convert-video-to-avi/).

Upload image(s) to Imgur.com. When the uploading is complete a box will pop up displaying various urls for the image, which can be copied and pasted. Zenity and Curl are required software.

* Name: Upload to Imgur
* Description: Upload image(s) to Imgur.com
* Command: 

`/home/$USER/Scripts/thunar-upload-to-imgur.sh -f %f`

Under `Appears if selection contains` make sure `Image Files` is checked.

Change `/home/$USER/Scripts/thunar-upload-to-imgur.sh` to the path of the bash script, and change `thunar-upload-to-imgur.sh` to the name you give the bash script.

###Bash Script

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script: thunar-upload-to-imgur.sh Save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type: `chmod +x thunar-upload-to-imgur.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](https://gist.github.com/pointpont/aeb579ffc69493c1792c)

