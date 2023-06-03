# ffmoeg命令大全
## 基础命令
-vn 表示禁止输出视频流，只输出音频流

-an 表示禁止输出音频流，只输出视频流

-acodec copy直接复制音频，而且不重新编码

-vcodec copy直接复制视频，厄切不重新编码
## GPU加速
ffmpeg -decoders | grep cuvid 列出支持cuda加速的编码器

## 画质
-qb 0~51，0是无损

## BGM
```
ffmpeg -hwaccel cuda -i pp.mp4 -i 1.ogg -filter_complex "[0:a]aformat=fltp:44100:stereo[0a];[1:a]aformat=fltp:44100:stereo[a1];[0a][a1]amerge=inputs=2[a]"  -c:v copy -map 0:v:0 -map "[a]" pp2.mp4 -y
```
## 添加音轨
```
ffmpeg -hwaccel cuda -i pp.mp4 -i 1.ogg -map 0:v:0 -map 0:a:0 -map 1:a:0 -c:v copy ppyg.mp4
```