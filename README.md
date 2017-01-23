# nvidia-patch

Binary patch for Nvidia Linux Display Driver which removes NVENC parallel sessions restriction and allows to have more than two simultaneous NVENC encoding processes. NVENC is a hardware H.264/H.265 encoder, see docs for details.

## Usage

```
user@host:~/nvidia-patch# ./patch.sh 
Usage: ./patch.sh <path to original libnvcuvid.so.xxx.yy> <destination for patched livnvcuvid.so.xxx.yy>
```

## See also

~~If you experience `CreateBitstreamBuffer failed: out of memory (10)`, then you have to lower buffers number used for every encoding session. If you are using `ffmpeg`, consider using this [patch](https://gist.github.com/Snawoot/70ae403716c698cb86ab015626d72bd4).~~
Since [this FFmpeg commit](https://github.com/FFmpeg/FFmpeg/commit/de2faec2faf34ee948d400101299d4ccdc1f3a50) patching of FFmpeg is not needed. It is possible to lower buffers number using `surfaces` option of command line interface.
