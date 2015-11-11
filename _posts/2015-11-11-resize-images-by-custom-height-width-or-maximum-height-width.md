---
layout: post
title: Resize Images by Custom Height/Width or Maximum Height/Width
tags:
- thunar custom action
- resize
- graphics
- YAD
- mogrify
- awk
- identify
- convert
category: posts
---
To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/convert-video-to-avi/).

##Resize Images by Custom Height/Width

This custom action resizes images by a custom height. The resized images are moved to a subfolder and the originals remain in the working folder. If resizing by width is desired then remove the `x` from the following part of the command: `x$CUSTOM_COMMAND` and change the text `Enter Height` to `Enter Width`. This custom action requires YAD and ImageMagick be installed.

* Name: Resize by Custom Height
* Description: Resizes image(s) by custom height 
* Command: 

`CUSTOM_COMMAND=$(yad --entry --title "Custom Command" --text "Enter Height:") ; 
mkdir %d/dir && cd %d; for file in %N; do convert "$file" -resize 
x$CUSTOM_COMMAND "dir/${file}"; done`

Under `Appears if selection contains` make sure `Image Files` is checked.

##Resize Images by Maximum Height/Width

This custom action resizes images by a maximum height. So in a folder of 10 images, if only one image has a height over 600 height only that image will be resized. NOTE: The resized image(s) will replace the original image(s), so make a copy of the original(s) before converting. To change to maximum height replace both instances of `600` in the below command. If resizing by maximum width is desired then remove the `x` from the following part of the command: `x600`. ImageMagick must be installed for this custom action.

* Name: Resize Images by Maximum Height/Width
* Command: 

`identify -format '%w %h %f\n' *.jpg | awk '$2 > 600 {sub(/^[^ ]* [^ ]* /, ""); print}' | tr '\n' '\0' | xargs -0 mogrify -resize 'x600>' %N`

Under `Appears if selection contains` make sure `Image Files` is checked.
