Setup DSLR as webcam

Installation:

Debian/Ubuntu
sudo apt-get install gphoto2 v4l2loopback-utils v4l2loopback-dkms ffmpeg

Arch Linux
pacman -S gphoto2 v4l-utils v4l2loopback-dkms ffmpeg

Loading this kernel module manually (through modprobe) means you will have to remember to modprobe every time you reboot.
To ensure this module is enabled when your system is booted, you need to edit one config file /etc/modules

Run on the terminal:
sudo modprobe v4l2loopback exclusive_caps=1 max_buffers=2

On /etc/modules, dslr-webcam as a new line paste this:
dslr-webcam

Using sudo create a new file /etc/modprobe.d/dslr-webcam.conf and attach this:
alias dslr-webcam v4l2loopback
options v4l2loopback exclusive_caps=1 max_buffers=2

To test gPhoto2
- List auto-detected cameras and the ports to which they are connected:
gphoto2 --auto-detect

- Summary of camera status:
gphoto2 --summary

Display the camera and driver abilities specified in the libgphoto2 database. Use --summary to query an overview of the camera:
gphoto2 --abilities

Test to capture with dslr:
gphoto2 --capture-image-and-download

Test to use webcam (specify what device):
gphoto2 --stdout --capture-movie | ffmpeg -i - -vcodec rawvideo -pix_fmt yuv420p -threads 0 -f v4l2 /dev/video2

To use on VLC:
Right click -> Open Media -> Open Capture Device -> assign Video device name sample /dev/video2 -> Play
