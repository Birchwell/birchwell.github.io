---
layout: post
title: Rename - Alphanumeric Sequence
category: posts
---
This command will rename all files in a directory using an alphanumeric sequence. The downside of this command is that any directory subfolders will be renamed, but not the contents of the subfolders. In the following command files will be renamed aa0001, aa0002, etc:

`c=0; for i in *; do let c++; mv "$i" "aa$(printf "%04d" $c)${i#"${i%.*}"}"; done`

