---
title: "Installing fonts for ImageMagick"
date: 2020-06-20T23:02:50+01:00
draft: true
toc: false
images:
tags:
  - imagemagick
  - linux
---
List fonts currently installed:

`$ convert -list font`

Install new fonts - for example:

`$ sudo apt install fonts-dejvu`

You then need to update the database used by **locate**:

`$ sudo updatedb`

Create a hidden subdirectory:

`$ mkdir ~/.magick && cd ./.magick`

Install a script from ImageMagick that does the heavy lifting:

`$ wget http://www.imagemagick.org/Usage/scripts/imagick_type_gen`

Run the perl script:

`$ perl ./imagick_type_gen > ~/.magick/type.xml`

And check the new fonts are present and correct by re-running:

`$ convert -list font`