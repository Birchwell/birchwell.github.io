---
layout: post
title: Jpegoptim - Resize Image to Size Threshold
category: posts
---
The following command will resize all jpgs in a folder. Any images that are over 4mb in size will be resized to 4mb, while overwriting originals. It will not touch jpgs that are under 4mb in size. Change `3800` to suit your needs. The program `jpegoptim` must be installed.

`jpegoptim -S3800 *.jpg`

The following command will also strip all metadata* from the jpgs:

`jpegoptim --strip-all -S3800 *.jpg`

---
*See also [Strip All Metadata with Exiftool](https://pointpont.github.io/exiftool/image/2015/06/12/exiftool-strip-all-metadata-from-images.html)
