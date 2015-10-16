---
layout: post
title: Thunar Custom Action - Securely Shred and Delete Files
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://birchwell.github.io/posts/thunar-custom-actions-tutorial-convert-video-to-avi/).

For secure deletion of files that can’t be recovered. The program Zenity must be installed for this action to work. The action will pop up a confirmation window.

* Name: Shred and Delete
* Description: Securely deletes file(s) that can’t be recovered.
* Command: 

`zenity --question;if [ $? = 0 ];then shred -fuz %F;fi`

Under `Appears if selection contains` make sure everything is checked.
