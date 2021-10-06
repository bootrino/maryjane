# MaryJane MJPEG server

MaryJane is a simple MJPEG server written in Python.

### Live demo:

https://htmlpreview.github.io/?https://github.com/bootrino/maryjane/index.html
<a href="https://htmlpreview.github.io/?https://github.com/bootrino/maryjane/index.html">
    Live demo of MaryJane
</a>

**Project status**:

Created 6 Oct 2021 by Andrew Stuart andrew.stuart@supercoders.com.au

License: MIT

You are welcome to post questions in the github issues but don't expect an answer - I may or may not be interested in reading/fixing issues.

**How it works**:

The server loads the same jpeg file from the file system and sends it to the web browser.

It does this continuously.

That's pretty much it.  It's less than 30 lines of code - have a look.

It is the responsibility of something else to keep replacing that file with the latest frame in the video stream.

For example, the following command reads frames from a video file and constantly replaces the output filename with the current frame:

ffmpeg -y -re  -stream_loop -1 -i monster-family-2-teaser_h480p.mov  -f image2 -update 1 /dev/shm/img.jpeg

