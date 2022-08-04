# 视频缩略图

::: tip

在视频快进或者想跳转到某个播放时间节点时，提前以一张缩略图的形式展示，MuiPlayer 支持在扩展插件中配置缩略图。

缩略图功能的实现实际上是由一张或者多张图片，图片由多个规则排列的视频片段构成，查看 youtube 等各视频媒体站点都是这样实现的，例如下图是一个 tile=6x5，scale=160x120 的缩略图。 

<img src="https://muiplayer.oss-cn-shanghai.aliyuncs.com/static/image/thumbnails_preview.png" class="zoom-custom-imgs" alt="视频缩略图"/>

:::



### 生成缩略图（FFmpeg）

使用 [FFmpeg](http://ffmpeg.org/) 处理视频是个很好的选择，这里使用它生成视频缩略图。如下命令即可创建 scale=160:90，tile=10x10 的视频缩略图：

```sh
ffmpeg -i video.mp4 -vsync vfr -vf "select=isnan(prev_selected_t)+gte(t-prev_selected_t\,1),scale=160:90,tile=10x10" -qscale:v 3 "output%03d.jpg"
```

| 属性名             | 类型   | 默认值   | 说明                                                         |
| ------------------ | ------ | -------- | ------------------------------------------------------------ |
| thumbnails         | Object | {}       |                                                              |
| thumbnails.preview | Array  | []       | 缩略图配置列表，接受可由多张按照顺序排列的缩略图片的资源地址 |
| thumbnails.tile    | Array  | [10,10]  | 指定缩略图排列规则                                           |
| thumbnails.scale   | Array  | [160,90] | 指定视频缩略片段图的尺寸<br/>默认值：[160,90] ，表示 width = 160px，height = 90px; |



### 使用缩略图

MuiPlayer 并不限制缩略图具有指定的规格大小，但是你需要给定缩略图的规范，scale 参数指定宽高比，tile 参数指定缩略图碎片的排列规则。

```javascript
let thumbnails = {
    preview:['./image/thumbnail001.jpg','./image/thumbnail002.jpg'], // 缩略图配置地址
    tile:[10,10], // 缩略图排列规则
    scale:[160,90], // 缩略片段图宽高比 
}

var mp = new MuiPlayer({
    container:'#mui-player',
    src:'../media/media.mp4',
    ...

    plugins:[
        new MuiPlayerMobilePlugin({
            thumbnails,
        }),
            
        new MuiPlayerWebpagePlugin({
            thumbnails,
        })
    ]
});
```



#### Other Doc：

- [参考一](https://www.bogotobogo.com/FFMpeg/ffmpeg_select_scene_change_keyframes_tile_Creating_a_mosaic_of_screenshots_from_a_movie.php)
- [参考二](https://superuser.com/questions/538112/meaningful-thumbnails-for-a-video-using-ffmpeg)
- [参考三](https://askubuntu.com/questions/377579/how-can-i-use-ffmpeg-to-output-a-screenshot-gallery-mosaic)