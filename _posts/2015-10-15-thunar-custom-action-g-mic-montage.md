---
layout: post
title: Thunar Custom Action - G'Mic Montage
tags:
- thunar custom action
- g'mic
- graphics
category: posts
---
![G'Mic Montage - Thunar Custom Action](http://i.imgur.com/306Q9j1l.jpg)

To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/thunar-custom-action-tutorial-convert-video-to-avi/).

[G’Mic (GreyC’s Image for Magic Computing)](http://gmic.eu/) is software for image processing that works on Linux, Mac and Windows. It can carry out a zillion functions on images, but I’m just going to focus on its montage tool, which I find superior to ImageMagick’s montage tool. To use the montage feature you must have G’Mic version 1.6.0.4 or above installed.

The montage above was created at the command line with this command:

`gmic *jpg -gimp_montage 4,\""V(H(0,1),H(2,V(3,4)))"\",1,1.0,0,5,0,0,0,255,0,0,0,0,0 -o output."$(date)".jpg,75`

In a matter of seconds it combined all JPGs in a folder to produce the above montage. Control the quality output by following output.jpg with, say, “,75″ which amounts to 75% quality. I can’t get the quality output function to work with my command for Thunar Custom Actions. So when creating montages with Thunar Custom Actions you’ll need to reconvert the output montage to smaller quality, unless you don’t mind a large filesize.

This part of the command:

`\""V(H(0,1),H(2,V(3,4)))"\"`

controls the layout of the images. I haven’t quite figured this out yet, but I like the way it lays out images, so I use it as my default. (You can use this tutorial to learn about possible commands using G’Mic plugin for GIMP in verbose mode.  I used this tutorial to figure out what default command I like best.)

This part of the command:

`,1,1.0,0,5,0,0,0,255,0,0,0,0,0`

has 13 values between commas representing different options.

* 1st placement: I can’t determine what this does.

* 2nd placement: Controls the size of the output montage. “1.0” will keep the original size of the images. I find that if the images have a larger dimension than 2000 pixels G’Mic has a hard time processing it and the computer freezes up (I use a Thinkpad with 2.5 ghz dual core processor and 8gb RAM), so it might be wise to use a smaller value to reduce the size of the montage. “.30″ will reduce the images by 30%, so the resulting montage will be 30% smaller.

* 3rd placement: Controls padding size. I usually keep this at zero.

* 4th placement: Controls the size of the framing in pixels. So 5 represents 5 pixel framing, and 75 represents 75 pixel framing, which is quite large. I usually keep this at 5.

* 5th-8th placements: Controls color of the framing, using 3 digit HEX values. I usually use “255” for the 8th placement value, and keep 5, 6, and 7th placements at zero.

* 9th placement: Controls rotation of images in a clockwise direction. With this function the montage will show the images rotated in a clockwise direction. I usually keep this value at zero.

* 10th placement: Controls random rotation of images. I usually keep this value at zero.

* 11th placement: Seems to control in what order images are arranged in the montage. I usually keep the value set to zero, in which case the images will appear in the montage in the order to which they’re alphanumerically named.

* 12th placement: Creates duplicates of each image in the folder and saves them to the parent folder, placing frames around each image. Unless you keep the value at zero, a montage isn’t created.
Thunar Custom Action – Create Montage of Selected Images

* 13th placement: Not sure what this does.

With this custom action you can right-click on selected JPGs and select the G’Mic Thunar Custom Action, which will automatically convert the images into a montage with 5px borders. An improvement on this command could be achieved with the incorporation of YAD, which would give you the option to input all sorts of variations in framing size, padding, rotation, colors, montage size. But I like this command for most uses, so I use it as my default. To learn more about Thunar Custom Actions click here. With the command-line version of the command the quality output can be controlled by following output.”$(date)”.jpg with, say, “,75″ which amounts to 75% quality. I can’t get the quality output function to work with the command for Thunar Custom Actions. So when creating montages with Thunar Custom Actions you’ll need to reconvert the output montage to smaller quality, unless you don’t mind a large filesize.

* Name: G’Mic Montage – 100%, 5px Frame
* Command: 

`gmic %N -gimp_montage 4,\""V(H(0,1),H(2,V(3,4)))"\",1,1.0,0,5,0,0,0,255,0,0,0,0,0 -o 0000."$(date)".jpg`

Under `Appearance Conditions` check `Image Files`.

##Thunar Custom Action – Create Montage of Directory Contents

This Custom Action works if you have a directory of images you want to make into a montage. Just right-click on the folder housing the images and click G’Mic Montage Folder Content. The montage will be saved within the respective folder (this works on multiple folders, though the system may freeze up if you run it on too many folders at once). The script currently works only with JPGs, but it can be modified to work with additional formats. With the command-line version of the command the quality output can be controlled by following output.”$(date)”.jpg with, say, “,75″ which amounts to 75% quality. I can’t get the quality output function to work with the command for Thunar Custom Actions. So when creating montages with Thunar Custom Actions you’ll need to reconvert the output montage to smaller quality, unless you don’t mind a large filesize. NOTE: Will not work on images with spaces in filenames. The Custom Actions [here](http://birchwell.github.io/posts/thunar-custom-action-slugify-and-remove-custom-characters/) are good for removing spaces and other characters from filenames.

* Name: G’Mic Montage Folder 
* Content
* Command: 

`/$USER/Scripts/montagefolders.sh %F`

Under `Appears if selection contains` make sure `Directories` and `Image Files` are checked.

Change `$USER/Scripts/montagefolders.sh` to the path of the bash script, and change `montagefolders.sh` to the name you give the bash script.

###Bash Script:

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `montagefolders.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type `chmod +x montagefolders.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](http://gist.github.com/Birchwell/b9805289893117345f1f)

##Thunar Custom Action - Create Multiple Montages of Images in Folder

This G'Mic script will go through a folder of many images and output multiple montages in the working folder. The script can be modified to customize the number of images to turn into individual montages by changing the `4` in `(expr $c % 4)` to whatever number desired. NOTE: Will not work on images with spaces in filenames. The Custom Actions [here](http://birchwell.github.io/posts/thunar-custom-action-slugify-and-remove-custom-characters/) are good for removing spaces and other characters from filenames.


* Name: G’Mic Multiple Montages
* Content
* Command: 

`/$USER/Scripts/gmicmultiplemontages.sh %N`

###Bash Script:

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `gmicmultiplemontages.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type `chmod +x gmicmultiplemontages.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](http://gist.github.com/Birchwell/8065b4561c98c5a8a5cf)
