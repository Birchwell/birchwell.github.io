---
layout: post
title: ZIP Archive with Limited Number of Files
category: posts
---
The following command will zip all files in a folder in batches of 500. The number 500 can be changed to any number that suits your needs. The program `parallel` must be installed for this command to work. At the command line type `sudo apt-get install parallel` and press `Enter`.

`find * ! -name "*.zip" -type f -print0 | parallel -0 -N 500 zip arch{#} {}`

