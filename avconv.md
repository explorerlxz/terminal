# avconv

```
avconv -f x11grab -r 25 -s 1280x720 -i :0.0+0,0 -vcodec libx264 -pre lossless_ultrafast -threads 0 video.mkv
```

> * **record video**! The command is learned from http://wiki.oz9aec.net/index.php/High_quality_screen_capture_with_avconv

```
avconv -f pulse -i alsa_output.pci-0000_00_1b.0.analog-stereo.monitor audio.wav
```

> * **record audio**

```
avconv -f pulse -ac 1 -i alsa_output.pci-0000_00_1b.0.analog-stereo.monitor -f x11grab -r 24 -s 1366x768 -i :0.0 -vcodec libx264 -crf 22 -acodec libmp3lame -ar 22050 -ab 63k grab1.mkv
```

> * **record audio & video!** This command doesn't work very well, the sound and video are not synchronize!

************

## Related commands

ffmpeg, pactl

```pactl
pactl list sources | grep analog-stereo.monitor
```
