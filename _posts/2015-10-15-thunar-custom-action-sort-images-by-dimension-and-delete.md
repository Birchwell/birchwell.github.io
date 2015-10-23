---
layout: post
title: Thunar Custom Action - Sort Images by Dimension and Delete
tags:
- thunar custom action
- YAD
- zenity
- graphics
- filesize
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-actions-tutorial-convert-video-to-avi/).

One of the downsides of Linux is that you can’t sort images by dimensions without some tinkering. This is easily done in Windows systems. With the help of the following bash script you can sort a folder of images according to dimensions.

I use this script with Thunar Custom Actions, which allows me to right-click in a directory of images (or select images and right-click) and sort them by their dimensions.

This script once had a working delete function, whereby you would check the boxes next to images, click OK, and those images would be deleted. For some reason this delete function hasn’t worked since I upgraded to Linux Mint 17.1. (There's a Zenity bash script below that does have a working delete function.) The images can be sorted according to name, height, or width. Double-clicking on a file will open the image in an image viewer of choice. I use XNViewMP, so I have added “xnview” (which is the name of XNViewMP’s executable in /bin) to the following part of the script:

`function dclick {
	xnview "$4" &`

##Thunar Custom Action - Sort Images by Dimension with YAD

![Sort Images by Dimension - Thunar Custom Action](http://i.imgur.com/N1MTaqo.png)

* Name: DimensionSort
* Description: Sort images by dimensions.
* Command: 

`/home/$USER/Scripts/dimensionsortyad.sh %f`

Under `Appearance conditions` check `Directories` and `Image Files`.

Change `/home/$USER/Scripts/dimensionsortyad.sh` to the path of the bash script, and change `dimensionsortyad.sh` to the name you give the bash script.

###Bash Script:

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `dimensionsortyad.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type `chmod +x dimensionsortyad.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions.

[YAD Bash Script](https://gist.github.com/Birchwell/0319caa7fbf198cd6120)

##Thunar Custom Action - Sort Images by Dimension and Delete with Zenity

I have another bash script that’s not quite as fast as the YAD script. It uses Zenity to sort images by dimension and it does allow you to delete images from within the sorting box, but does not allow you to double-click the images and open them in a viewer. 

![Sort Images by Dimension - Thunar Custom Action](http://i.imgur.com/YO1kJRH.png)

The amount of images it sorts is adjustable in the script. Right now it’s set to sort 500 images `(MAX_INPUT=500)`, but you can change this to any number. There are two instances of `MAX_INPUT=`. Change the number in both instances. You can also set how many images you want to delete. This is changed by modifying the number after `MAX_OUTPUT=`. The number is currently set at 100. So if you chose to delete 150 images, only 100 would be deleted. Change the numbers after both instances of `MAX_OUTPUT=`. To select images listed nonconsecutively for deletion use `CTRL+left-click`. To select consecutively listed images for deletion click on the first image in the series and then `SHIFT+left-click` on the last image. All the images in between will highlight. In which case you can press `OK` to delete them.

This script can be used with Thunar Custom Actions. Just follow the directions above and modify them for this script.

[Zenity Bash Script](https://gist.github.com/Birchwell/28b7c9f5bb64d9595d75)
