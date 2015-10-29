---
layout: post
title: Thunar Custom Action - Slugify and Remove Custom Characters
tags:
- thunar custom action
- delete
- sed
- rename
category: posts
---
To learn how to use Thunar Custom Actions click [here](http://birchwell.github.io/posts/thunar-custom-action-tutorial-convert-video-to-avi/).

##Delete Spaces, Underscores, Plusses, and Hyphens in Filenames

This custom action will remove spaces, underscores, plusses, and hyphens from selected filenames. It can be customized by deleting or adding characters between the brackets: `[ _+-]`. So if you want to just delete spaces and plusses, then remove the underscore and the hyphen from between the brackets.

* Name: Delete _ +-
* Description: Remove custom characters from selected filenames.
* Command:

~~~~~~~
for file in %N; do mv "$file" `echo $file | sed -e 's/[ _+-]//g'`; done
~~~~~~~

Under `Appears if selection contains` make sure everything is checked.

##Slugify Filenames

Modifies filenames to lowercase, replaces spaces with dashes, and lowercases extension.

* Name: Slugify
* Description: Modifies filenames to lowercase, replaces spaces with dashes, and lowercases extension.
* Command: 

~~~~~~~~~~~~
for file in %N; do mv "$file" "$(echo "$file" | tr -s ' ' | tr ' A-Z' '-a-z' | tr
-s '-' | tr -c '[:alnum:][:cntrl:].' '-')"; done
~~~~~~~~~~~~

Under `Appears if selection contains` make sure everything is checked.
