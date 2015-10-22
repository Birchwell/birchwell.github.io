---
layout: post
title: FFMPEG - Capturing Video Frames
tags:
- ffmpeg
- video
- capture
category: posts
---
These are two FFmpeg video frame capturing scripts that work for me. They probably work with any type of video file, but I’ve confirmed that they work with FLV, AVI, and MP4 files.

##Capture Custom Number Frames in Sequence

`ffmpeg -i input.mp4 -vframes 550 images%d.jpg`

This command will capture frames in sequence from the beginning of the video.

`-i` is the parameter which designates the directory which contains the video file. You can follow this parameter with just the name of the video file if the terminal prompt is directed to the folder which contains the video file. So if the video file is in `Desktop/FFmpeg/ppp.mp4`, then the following can be typed into the command prompt: `cd Desktop/FFmpeg`. Hit `enter`, and the prompt will now be at the FFmpeg folder which contains the video file. In which case the `-i` parameter would not need to be followed by `Desktop/FFmpeg`, but merely the name of the video file.

`-vframes` is a parameter that designates the number of video frames to be captured. “550” is the number of frames which will result, but this can be changed to any number up to the number of total frames in the video file.

`images%d.jpg` will give unique names to the screenshots: images1.jpg, images2.jpg, images3.jpg. Another naming option: `images%05d.jpg`, in which the output would be images00001.jpg, images00002.jpg, images00003.jpg . . . .

NOTE: The image format for both commands can be changed to other formats, such as PNG.

##Capture Custom Number of Frames Over Custom Time Span

`ffmpeg -ss 00:10:48 -t 00:00:05.00 -i input.mp4 -r 25.0 images%5d.jpg`

`-r` designates frame rate of the video from which frames are to be captured. For a video with a framerate of 25, put 25.0 after the -r parameter.

`-ss` sets the start time for frame capture.

`-t` sets the duration of frame capture.

In the command above the video will begin capturing at 10 minutes, 48 seconds. And it will continue capturing for 5 seconds and then stop. Both the `–ss` time parameter and the `-t` time parameter can be changed.

If you want to control the quality of the output images:

`[-qscale:v 2]` or the alias `-q:v 2` controls quality of image output. 1-31, with 31 being the worst quality.

`ffmpeg -ss 00:10:48 -t 00:00:05.00 -i input.mp4 -r 25.0 qscale:v 2 images%5d.jpg`
