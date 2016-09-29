# avconv

### 录制视频

```
avconv -f x11grab -r 25 -s 1280x720 -i :0.0+0,0 -vcodec libx264 -pre lossless_ultrafast -threads 0 video.mkv
```

> * **record video**! The command is learned from http://wiki.oz9aec.net/index.php/High_quality_screen_capture_with_avconv

### 录制音频


```
avconv -f pulse -i alsa_output.pci-0000_00_1b.0.analog-stereo.monitor audio.wav
```

> * **record audio**

```
avconv -f pulse -ac 1 -i alsa_output.pci-0000_00_1b.0.analog-stereo.monitor -f x11grab -r 24 -s 1366x768 -i :0.0 -vcodec libx264 -crf 22 -acodec libmp3lame -ar 22050 -ab 63k grab1.mkv
```

### 截取一段视频

只把视频的前后减去一段，视频不进行转码。说白了就是跟摘豆角一样--掐头去尾。

ffmpeg复杂的参数里面有 -ss 和 -t 实现这个功能：

 avconv -ss 00:00:00  -i 原文件.mp4 -codec copy  -t 00:12:50 新文件.MP4

关键是
-ss 必须在 -i 之前
-t 必须在 -code后面
-code 必须在 输出文件之前
强大的ffmpeg分分钟就搞定巨大的视频切割，完全不用类似会声会影的软件解码再编码了。

ffmpeg -ss 01:00:00 -i input_file_h264.mp4 -vcodec copy -acodec copy -t 00:06:00 output_file.mp4

### 旋转视频

手机拍摄的视频有时候到电脑上播放不方便，主要是视频方向不对

顺时针旋转90度

ffmpeg -i demo.mp4 -vf "transpose=1" o.mp4

顺时针旋转180度

ffmpeg -i demo.mp4 -vf "transpose=2" o.mp4


### 添加背景音乐

mencoder -ovc copy -audiofile background.mp3 -oac copy video.avi -o output.avi

> * **record audio & video!** This command doesn't work very well, the sound and video are not synchronize!


```
avconv -i *.mp4 output.mp3
```

> convert mp4 file to mp3 file

************

## Related commands

ffmpeg, pactl

```pactl
pactl list sources | grep analog-stereo.monitor
```

## Reference

- [ffmpeg/avconv 轉檔與影片連接範例](http://rocksaying.tw/archives/22568176.html)
- stackoverflow[add background music to existing avi](http://stackoverflow.com/questions/20863703/add-background-music-to-existing-avi)
- [ffmpeg分割视频的方法](https://wuyuans.com/2012/04/ffmpeg-split)
