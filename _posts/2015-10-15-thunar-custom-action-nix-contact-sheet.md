---
layout: post
title: Thunar Custom Action - NIX Contact Sheet
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-actions-tutorial-convert-video-to-avi/).

This Custom Action will produce contact sheets of videos using a bash script I found [here](http://p.outlyer.net/vcs/#issues).

* Name: Nix Contact Sheet
* Description: Create contact sheet for videos.
* Command: 

`/home/$USER/Scripts/nix.sh -n 42 -c 3 -j %F`

Under `Appears if selection contains` make sure `Video Files` is checked.

Change `/home/$USER/Scripts/nix.sh` to the path of the bash script, and change `nix.sh` to the name you give the bash script. `-n 42` stands for the number of captures taken. If you want, say, 60 captures then replace 42 with 60. `-c 3` stands for 3 columns. This can be changed to any number of columns. `-j` stands for jpg, which will be the output format of the contact sheet. If you want it output as png, then remove `-j`, as png is the default. 

###Bash Script

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script: `nix.sh`. Save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type: `chmod +x nix.sh` And press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](https://gist.github.com/Birchwell/f9372759efe5dcbc8d32)
