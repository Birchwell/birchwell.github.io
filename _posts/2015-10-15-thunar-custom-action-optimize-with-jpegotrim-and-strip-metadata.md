---
layout: post
title: Thunar Custom Action - Optimize with Jpegotrim and Strip Metadata
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://pointpont.github.io/thunar_custom_action/video/ffmpeg/conversion/2015/06/08/thunar-custom-actions-tutorial-convert-video-to-avi.html).

Losslessly optimize JPEGs, by optimizing the Huffman tables and stripping comments and EXIF metadata from the file. If you don't want to strip metadata then just remove `--strip-all` from the command.

* Name: Optimize with Jpegoptim (Strip Metadata)
* Description: Losslessly optimize JPEGs, by optimizing the Huffman tables and stripping comments and EXIF metadata from the file.
* Command: `for file in %F; do jpegoptim --strip-all -of "$file"; done`

Under `Appears if selection contains` make sure `Image Files` is checked.