# Bayesian Hls Manager

# Example
```PHP
$keyframeStr = '50';
$playListName = "{$name}_pl.m3u8";
$readyName = "{$name}.ready";
$segmentList = "{$downloadPath}{$playListName}";
$segmentTime = 10;
$segmentName = "{$downloadPath}{$name}_sg%06d.ts";

// Replace {} to input_file.mkv
$convert = "ffmpeg -y -i {} -pix_fmt yuv420p -c:v copy -c:a copy -bsf:v h264_mp4toannexb -force_key_frames $keyframeStr -f segment -segment_list $segmentList -segment_time $segmentTime -segment_list_type m3u8 -strict -2 segmentName";
```

```
CMD
ffmpeg -i input_file.mkv -an -c:v libx264 -b:v 1M -preset slow -vf scale=-1:720 output_file.mp4
```
