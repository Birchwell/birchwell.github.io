---
layout: post
title: Thunar Custom Action - Rename Jpeg/JPG to Lowercase jpg
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://pointpont.github.io/thunar_custom_action/video/ffmpeg/conversion/2015/06/08/thunar-custom-actions-tutorial-convert-video-to-avi.html).

This custom action will rename images with JPEG and JPG extensions with jpg.

* Name: Rename JPEG, JPG to jpg
* Description: Sort images by dimensions.
* Command: `rename 's/\.jpe?g$/.jpg/i' * %F`

Under `Appearance conditions` check `Image Files`.
