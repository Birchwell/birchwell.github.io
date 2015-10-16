---
layout: post
title: Thunar Custom Action - Split Video Into Pieces
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://pointpont.github.io/thunar_custom_action/video/ffmpeg/conversion/2015/06/08/thunar-custom-actions-tutorial-convert-video-to-avi.html).

This custom action will split video into clips according to a user defined number of seconds. The duration of the clips will not always be exactly the duration wanted. This is because of keyframes.

![image](http://i.imgur.com/DzqyJKr.png)

* Name: Split Video
* Description: Split video into clips at defined time intervals
* Command: `/home/$USER/Scripts/splitvideoyad.sh %f`

Under `Appears if selection contains` make sure `Video Files` is checked.

###Bash Script

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `splitvideoyad.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type chmod +x `splitvideoyad.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](https://gist.github.com/pointpont/ffaba4200eced3145447)