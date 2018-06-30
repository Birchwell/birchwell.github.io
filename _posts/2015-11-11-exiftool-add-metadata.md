---
layout: post
title: Exiftool - Add Metadata
tags:
- thunar custom action
- exiftool
- graphics
- metadata
- flickr
- YAD
category: posts
---

To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/tutorial-convert-video-to-avi).

##Exiftool - Add Metadata

Add metadata to images using Exiftool with YAD. There are 18 fields, 9 fields for entering keywords. All keyword fields must be populated, otherwise no keywords will be applied to the image(s). I haven't figured out how to solve that issue. After applying metadata to images copies will be created in the working directory, appended with `_original`. [Filenames with spaces](http://birchwell.github.io/posts/thunar-custom-action-slugify-and-remove-custom-characters/) will not work with this bash script. This bash script is useful with images that will be uploaded to Flickr, as the metadata fields line up with those Flickr uses to populate data.

![Exiftool - Thunar Custom Action](http://i.imgur.com/6IbOvjD.png)

Fields can be populated by default with information. For example, the first 8 fields in the first column (above) will often require the same information for every image to which you add metadata.

To change the default information open up the bash script and replace the information between quotes with your own information:

`"John Doe" "(c) 2015 John Doe" "Chicago" "Illinois" "United States" "John Doe" "(c) 2015 John Doe" "John Doe"`

If you don't want those fields automatically populated with information then delete the above code from the bash script.

##Thunar Custom Action

* Name: Exiftool
* Description: Add metadata to images
* Command: 

`/$USER/Scripts/exiftooladdmetadata.sh %N`

Change `$USER/Scripts/exiftooladdmetadata.sh` to the path of the bash script, and change `exiftooladdmetadata.sh` to the name you give the bash script. Under `Appears if selection contains` make sure `Image Files` is checked.

###Creating Bash Script:

I keep my bash scripts in a folder named Scripts in my personal directory. To create the bash script copy the script below and paste it into a text editor. Name the script `exiftooladdmetadata.sh` and save it to the scripts folder you created. Make the script executable by opening up a terminal and navigating to the folder in which the script is stored. Type `chmod +x exiftooladdmetadata.sh` and press `Enter`. The script will now work when used with Thunar Custom Actions. To learn more about Thunar Custom actions click here.

[Bash Script](http://gist.github.com/Birchwell/8d8e4b8ca7722c28d193)

See also [Exiftool - Strip Metadata from Image](https://birchwell.github.io/posts/exiftool-strip-all-metadata-from-images/).
