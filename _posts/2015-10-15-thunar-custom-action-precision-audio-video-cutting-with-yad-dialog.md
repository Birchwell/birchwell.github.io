---
layout: post
title: Thunar Custom Action - FFMPEG Precision Audio/Video Cutting with YAD Dialog
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-actions-tutorial-convert-video-to-avi/).

This bash script skirts the annoying FFmpeg limitation of cutting audio or video based not on start/stop timestamps, but on seconds elapsed. For example, this is the FFmpeg command to extract a video clip from a video:

`ffmpeg -ss 00:10:48.123 -t 00:00:05.000 -i input.mp4 -c:v libx264 output.mp4`

Or the command for FFmpeg versions older than 2.5:

`ffmpeg -i input.mp4 -ss 00:10:48.123 -t 00:00:05.000 -c:v libx264 output.mp4`

The above command will cut a video starting at 10 minutes, 48 seconds, 123 milliseconds. Then it will cut 5 seconds from the video, represented by `-t 00:00:05.000`.

But it’s often much more convenient to use start/stop timestamps. With the following bash script you can enter a start time to begin the cut, and an end time to terminate the cut, which removes the sometimes necessary task of performing math to determine precisely how many seconds you need cut.

##Thunar Custom Action

I use the following bash script with Thunar Custom Actions, but it can be used alone as a bash script. Make sure you have YAD (Yet Another Dialog) installed. More on Custom Actions here.

###Chop Audio/Video

When right-clicking on an audio or video file and selecting the Chop Audio/Video custom action, a dialog box will appear, and an audio or video file must be selected. Any audio and video format that FFmpeg supports can be added to the bash script. Presently MP4, AVI, MKV, and MP3 are included, so any files with those formats will appear when searching for files through the YAD dialog box. After selecting the file another dialog box will pop up to enter start/stop timestamps (in hh:mm:ss format) and for setting the output directory and output filename (click the folder icon to the far right of the output box).

![image](http://i.imgur.com/zXkfHrp.png)

* Name: Chop Audio/Video
* Description: Cut video using start/stop times
* Command: 

`/$USER/Scripts/chopvideoaudio.sh %N`

Under `Appears if selection contains` make sure `Audio Files` and `Video Files` are checked.

Change `$USER/Scripts/chopvideoaudio.sh` to the path of the bash script, and change `chopvideoaudio.sh` to the name you give the bash script.

###Bash Script:

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `chopvideoaudio.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type `chmod +x chopvideoaudio.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](https://gist.github.com/pointpont/91151304bcc6be5b76e5)

Any format that FFmpeg supports can be added to the bash script. So if you want to add the .flv format just insert it after the file-filter parameter. If you want to encode the clip instead of copying it (which is useful if you want to create more keyframes to make use of cutting to the millisecond) then replace -c:v copy with -c:v libx264, or whatever codec you want to use. More [here](http://superuser.com/questions/458761/accurately-cut-video-files-from-command-line) for tweaking the timestamp in the script to make use of milliseconds.
