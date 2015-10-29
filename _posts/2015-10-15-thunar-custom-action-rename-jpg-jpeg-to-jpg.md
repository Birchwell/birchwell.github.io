---
layout: post
title: Thunar Custom Action - Rename Jpeg/JPG to Lowercase jpg
tags:
- thunar custom action
- rename
- graphics
category: posts
---
To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/thunar-custom-action-tutorial-convert-video-to-avi/).

This custom action will rename images with JPEG and JPG extensions with jpg.

* Name: Rename JPEG, JPG to jpg
* Description: Sort images by dimensions.
* Command: 

`rename 's/\.jpe?g$/.jpg/i' * %F`

Under `Appearance conditions` check `Image Files`.
