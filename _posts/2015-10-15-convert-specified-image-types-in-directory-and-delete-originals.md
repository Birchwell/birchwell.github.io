---
layout: post
title: Convert Images with Particular Formats and Delete Originals
category: posts
---
The following command will convert any .bmp and .png images in a directory to .jpg, and delete the originals. ImageMagick must be installed.

`echo *.{bmp,png} | while read FILENAME;
do
convert ${FILENAME} ${FILENAME%.}.jpg
rm ${FILENAME};
done`

