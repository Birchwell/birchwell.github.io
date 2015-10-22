---
layout: post
title: Thunar Custom Action - Convert Images to MP4 Slideshow
tags:
- thunar custom action
- graphics
- video
- ffmpeg
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-actions-tutorial-convert-video-to-avi/).

This FFmpeg command will convert JPGs (or other formats) in a directory to an MP4 video (which can be handy for archiving purposes, slideshows, timelapse, et cetera), while retaining the correct scale of the images through the use of padding. The images will only be resized to a smaller dimension if the scaling and padding properties in the command are smaller than the image dimensions. So if the largest image is 3200×3800 pixels, and the scaling and padding is smaller than 3200×3800, then that image will be resized down. The resulting MP4 will often have a slightly smaller filesize than the combined filesize of the images. If you want to extract the images from the video at some point it should be noted that the black margins will be retained in the output frames.

Successful encoding of all images can be determined by multiplying the frames per second by the seconds in the video.

In the command directly below the frame rate is set to 15 frames per second. If you want to create a slideshow you might want to change it to 1 or 2 frames per second. This command makes use of the libx264 codec. I assume you could use some other codec. I haven’t tried it with PNGs, but it should work with any image format that FFmpeg supports. So change ‘*.jpg’ to any image type you want to work with. It should also work with any video format that FFmpeg supports, though I’ve only used it with MP4.

`ffmpeg -framerate 15 -pattern_type glob -i '*.jpg' -vf "scale=min(1920/iw\,1920/ih)*iw:min(1920/iw\,1920/ih)*ih,pad=1920:1920:(1920-(min(1920/iw\,1920/ih)*iw))/2:(1920-(min(1920/iw\,1920/ih)*ih))/2" -c:v libx264 output.mp4`

The dimensions are 1920×1920. The dimensions of the scale and padding can be modified. In the command below the dimensions are 1600×900 and the framerate is 5:

`ffmpeg -framerate 5 -pattern_type glob -i '*.jpg' -vf "scale=min(1600/iw\,900/ih)*iw:min(1600/iw\,900/ih)*ih,pad=1600:900:(1600-(min(1600/iw\,900/ih)*iw))/2:(900-(min(1600/iw\,900/ih)*ih))/2" -c:v libx264 output.mp4`

In the example below I have converted 99 JPGs of desserts (with a combined filesize of 9.7MB) to an MP4 video. The frame rate is set to 15, the video dimension is 1920×1920, and the MP4 filesize is 10.7MB:

[Example](http://preview.tinyurl.com/oentrdc)

##Thunar Custom Action

This command, like any command, can be converted to a Thunar Custom Action.

Learn how to use Thunar Custom Actions here.

* Name: JPG to MP4
* Description: Convert folders of JPG images to MP4.
* Command: 

`for file in %N; do ffmpeg -framerate 15 -pattern_type glob -i '*.jpg' -vf "scale=min(1920/iw\,1920/ih)*iw:min(1920/iw\,1920/ih)*ih,pad=1920:1920:(1920-(min(1920/iw\,1920/ih)*iw))/2:(1920-(min(1920/iw\,1920/ih)*ih))/2" -c:v libx264 output.mp4; done`

Under `Appearance Conditions` check `Image Files`.
