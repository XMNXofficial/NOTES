# ffmoeg命令大全
## 基础命令
-vn 表示禁止输出视频流，只输出音频流

-an 表示禁止输出音频流，只输出视频流

-acodec copy直接复制音频，而且不重新编码

-vcodec copy直接复制视频，厄切不重新编码
## GPU加速
ffmpeg -decoders | grep cuvid 列出支持cuda加速的编码器

