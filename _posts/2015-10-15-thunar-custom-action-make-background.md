---
layout: post
title: Thunar Custom Action - Set Image as Desktop Background
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://pointpont.github.io/thunar_custom_action/video/ffmpeg/conversion/2015/06/08/thunar-custom-actions-tutorial-convert-video-to-avi.html).

Set image as desktop background. It helps if the image is the exact dimension of your desktop, because this command does not allow you to customize how the image is displayed. If it’s not the right dimension you’ll have to go to your display properties and fidget with the options.

* Name: Set as background
* Description: Set image as desktop background
* Command: `xfconf-query -c xfce4-desktop -p /backdrop/screen0/monitor0/image-path -s %f`

Under `Appears if selection contains` make sure Image Files is checked.
