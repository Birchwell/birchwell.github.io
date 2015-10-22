---
layout: post
title: Jpegoptim - Resize Image to Size Threshold
tags:
- jpegoptim
- resize
- graphics
- metadata
category: posts
---
The following command will resize all jpgs in a folder. Any images that are over 4mb in size will be resized to 4mb, while overwriting originals. It will not touch jpgs that are under 4mb in size. Change `3800` to suit your needs. The program `jpegoptim` must be installed.

`jpegoptim -S3800 *.jpg`

The following command will also strip all metadata* from the jpgs:

`jpegoptim --strip-all -S3800 *.jpg`

---
*See also [Strip All Metadata with Exiftool](https://birchwell.github.io/posts/exiftool-strip-all-metadata-from-images/)
