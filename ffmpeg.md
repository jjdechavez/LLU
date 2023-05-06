Screencast with ffmpeg(to learn more `man ffmpeg`)

-f - means format
-s - size of screen(make sure put -s flag before -i flag)
-i - infile
last argument the file name of outfile

Capture without sound command:
ffmpeg -f x11grab -s 1920x1080 -i :0.0 out.mkv

Capture with sound(Built in) command:
ffmpeg -f pulse -ac 2 -i default -f x11grab -r 30 -s 1920x1080 -i :0.0 -acodec pcm_s16le -vcodec libx264 -preset ultrafast -threads 0 -y output.mkv 

Capture with specify hardware like microphone with -f alsa -i hw:0
ffmpeg -f x11grab -s 1920x1080 -i :0.0 -f alsa -i hw:0 out.mkv

Capture with specify webcam
ffmpeg -f x11grab -s 1920x1080 -i :0.0 -f alsa -i hw:0 -i /dev/video2 out.mkv

Puts everything camera, audio, Screencast (Delay camera)
ffmpeg -f alsa -i pulse -f x11grab -s 1920x1080 -r 30 -i :0.0+0,0 -vf "movie=/dev/video2:f=video4linux2, scale=480:-1, fps, setpts=PTS-STARTPTS [movie]; [in][movie] overlay=main_w-overlay_w-2:main_h-overlay_h-2 [out]" -vcodec libx264 -crf 20 -preset veryfast -threads 0 ~/Desktop/video1.mkv

Tips:
to get your dimensions of your screensize you can use xdpyinfo | grep dimensions | awk '{print $2;}'

List hardware available
arecord -l

xdpyinfo - display information utility
grep dimensions - filter and get the dimenseions
awk '{print $2;}' - get the second argument
