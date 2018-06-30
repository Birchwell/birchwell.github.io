---
layout: post
title: Securely Shred and Delete Files
tags:
- thunar custom action
- zenity
- shred
- fuz
- delete
category: posts
---
To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/tutorial-convert-video-to-avi).

For secure deletion of files that can’t be recovered. The program Zenity must be installed for this action to work. The action will pop up a confirmation window.

* Name: Shred and Delete
* Description: Securely deletes file(s) that can’t be recovered.
* Command: 

`zenity --question;if [ $? = 0 ];then shred -fuz %F;fi`

Under `Appears if selection contains` make sure everything is checked.
