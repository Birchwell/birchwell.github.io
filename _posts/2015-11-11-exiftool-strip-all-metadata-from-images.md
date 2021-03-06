---
layout: post
title: Exiftool - Strip Metadata From Images
tags:
- exiftool
- metadata
- delete
- graphics
category: posts
---
The following Exiftool command will strip all metadata* (XMP, EXIF, IPTC) from all images found in a folder. Exiftool must be installed.

`exiftool -all= -overwrite_original *.jpg *.JPG *.jpeg *.JPEG *.png *.PNG *.gif`

The following command will move stripped image files into a new subdirectory, while not moving files that have errors:

`exiftool -o allmetadatastripped/ -all= -overwrite_original *.jpg *.JPG *.jpeg *.JPEG *.png *.PNG *.gif`

---

*See also [Jpegoptim](http://birchwell.github.io/posts/resize-jpg-images-to-size-threshold/)
