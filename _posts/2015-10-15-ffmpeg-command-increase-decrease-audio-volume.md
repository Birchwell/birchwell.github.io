---
layout: post
title: FFMPEG - Manipulate Audio Volume
tags:
- ffmpeg
- audio
- volume
category: posts
---
The following command will increase audio volume. Change to `volume=0.5` to halve its normal volume, or `volume=2.0` to increase the normal volume two times.

`ffmpeg -i input.mp3 -af 'volume=2.0' output.mp3`

