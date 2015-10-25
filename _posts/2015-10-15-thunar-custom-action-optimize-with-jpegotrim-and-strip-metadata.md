---
layout: post
title: Thunar Custom Action - Optimize with Jpegotrim and Strip Metadata
tags:
- thunar custom action
- jpegoptim
- metadata
- delete
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-action-tutorial-convert-video-to-avi/).

Losslessly optimize JPEGs, by optimizing the Huffman tables and stripping comments and EXIF metadata from the file. If you don't want to strip metadata then just remove `--strip-all` from the command.

* Name: Optimize with Jpegoptim (Strip Metadata)
* Description: Losslessly optimize JPEGs, by optimizing the Huffman tables and stripping comments and EXIF metadata from the file.
* Command: 

`for file in %F; do jpegoptim --strip-all -of "$file"; done`

Under `Appears if selection contains` make sure `Image Files` is checked.
