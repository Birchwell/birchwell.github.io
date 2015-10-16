---
layout: post
title: Thunar Custom Action - Moving Files
category: posts
---
To learn how to use Thunar Custom Actions click [here](https://pointpont.github.io/thunar_custom_action/video/ffmpeg/conversion/2015/06/08/thunar-custom-actions-tutorial-convert-video-to-avi.html).

##Move To

This is a handy action which can move any selected files. A window will appear akin to the save to window in browsers. The program Zenity must be installed for this action to work.

* Name: Move To
* Description: Move selected files
* Command: `mv %f "'zenity --file-selection --directory'"`

Under `Appears if selection contains` make sure everything is checked.

##Move to Subfolder

This is a handy action which can move any selected files to a subfolder. The subfolder is created automatically, being given a name based on the date and time.

* Name: Move To Subfolder
* Description: Move selected files automatically
* Command: `NOW=$(date +"%%Y-%%m-%%d-%%H%%M%%S"); mkdir -p %d/$NOW; for file in %N; do mv -n "$file" -t "$NOW"; done`

Under `Appears if selection contains` make sure everything is checked.

##Move To Subfolder with Custom Name

This is a handy action which can move any selected files to a custom named subfolder. A dialog box will pop up, in which a custom name for the subfolder is entered. The program Zenity must be installed for this action to work.

* Name: Move To Custom Named Subfolder
* Description: Move selected files to custom named folder
* Command: `variable=$(zenity --entry --title="Create folder" --text="Name of the folder"); mkdir -p "$variable"; mv -n %F -t "$variable";`

Under `Appears if selection contains` make sure everything is checked.

##Files Into Folders

Divide files in folder into many folders. Customizable by changing number of files. Useful when dealing with a folder with tons of images, making browsing more manageable. In the bash script below change `1000` in `[ $c -eq 1000 ]` to a custom number based on the amount of files you want divided among subfolders.

* Name: Files into Folders
* Description: Divide files in folder into many folders.
* Command: `/home/$USER/Scripts/movefilesdir.sh %N`

Under `Appears if selection contains` make sure everything is checked.

###Bash Script

I keep my bash scripts in a folder called “Scripts” in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `movefilesdir.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type `chmod +x movefilesdir.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions.

[Bash Script](https://gist.github.com/pointpont/0bd07d007f42bf9750ce)

##Copy to Custom Named Subfolder

This is a handy action which can copy any selected files to a custom named subfolder. A dialog box will pop up, in which a custom name for the subfolder is entered. The program Zenity must be installed for this action to work.

* Name: Copy To Subfolder
* Description: Copy selected files to custom named subfolder
* Command: `variable=$(zenity --entry --title="Create folder" --text="Name of the folder"); mkdir -p "$variable"; cp -r -n %F -t "$variable";`

Under `Appears if selection contains` make sure everything is checked.

##Move files from subfolders to parent folder

This is a handy action which will move all files out of subfolders into their parent directory. It should be noted that this works on all subfolders. So if you have 10 subfolders and you right-click on one subfolder and choose this Custom Action then all files in all 10 folders will be moved to the parent folder.

* Name: Move files from subfolders to parent folder
* Description: Move files from subfolders to parent folder
* Command: `find . - mindepth 2 -type f -exec mv "{}" . \; && fin d . - type d -empty -delete`

Under `Appears if selection contains` make sure just `Directories` is checked.
