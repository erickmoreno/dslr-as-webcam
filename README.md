# DSLRs as webcams

How to make DSLRs works as webcams  
This is the main [reference](https://medium.com/nerdery/dslr-webcam-setup-for-linux-9b6d1b79ae22)

## Ubuntu

```bash
$ sudo apt install gphoto2 v4l2loopback-utils ffmpeg
$ sudo modprobe v4l2loopback exclusive_caps=1 max_buffers=2
$ gphoto2 --stdout --capture-movie | ffmpeg -i - -vcodec rawvideo -pix_fmt yuv420p -threads 0 -f v4l2 /dev/video1
```

Now you'll be able to see your DSLR as input stream soure on /dev/video1

#### Usefull gphoto2 commands

```
$ gphoto2 --shell
$ gphoto2 --list-config
$ 
```


## Mac os

- Install [Camera Live](https://github.com/v002/v002-Camera-Live/releases/tag/13) gphoto2 version
- Install [CamTwist](http://camtwiststudio.com/download/)
- 
