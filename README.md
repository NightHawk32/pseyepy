#### A python API for acquisition, display, and saving of video from the PS3Eye camera.

If you're making use of this package, please let me know! 

I'll be motivated to improve and maintain it if people are benefiting from it.

Reach me at: deverett[at]princeton[dot]edu

### About this package
----------------------

*pseyepy* is a lightweight, cross-platform, and open-source Python interface to the Playstation PS3Eye USB camera.

At this point, the dependencies for the project are:
  * python 3x
  * numpy
  * [libusb](http://libusb.info/)
  * (a substantially modified version of the) [PS3EYEDriver project](https://github.com/inspirit/PS3EYEDriver)
  * [ffmpeg](https://www.ffmpeg.org/)

The important features are:
  * stream simultaneously from as many cameras as you have available usb ports
  * frame rates: up to 150 Hz
  * resolutions: 640x480 or 320x240 pixels 
  * control of camera settings include gain, exposure, white balance, orientation, etc.
  * high-resolution software timestamps  
  * simple gui for real-time video display 
  * save movies to disk

### Working notes for documentation:
--------------------------------
  * The PSEye camera has two LED indicators: a blue light indicating power, and a red light indiciating communication with the computer.
  * If the cameras or API act strangely, try disconnecting and reconnecting the cameras, restarting the Python shell, and running the program again.
  * In general it is recommended to restart the python process before each camera use; it's not technically necessary but it helps avoid some issues.
  * The on-board camera settings can be wonky; changing them in a particular order can have specific effects, that sometimes prove irreversible until you restart the program.
  * The Stream writer currently can drop ~0.01% of frames (likely from the very end only, still unclear)

### TODO
--------
  * more documentation
  * build a multithreaded cython option for camera streaming to free the main process
  * importantly: without a threading implementation, Stream to file with cameras of different framerates will result in lowest for all
