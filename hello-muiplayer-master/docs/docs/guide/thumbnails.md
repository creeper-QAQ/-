# Video thumbnail

::: tip

When the video is fast-forwarded or you want to jump to a certain playback time node, it is displayed in the form of a thumbnail in advance. MuiPlayer supports the configuration of thumbnails in the extension plug-in.

The thumbnail function is actually implemented by one or more pictures. The pictures are composed of multiple regularly arranged video clips. This is how you can view various video media sites such as youtube. For example, the picture below is a tile=6x5, scale =160x120 thumbnail.

<img src="https://muiplayer.oss-cn-shanghai.aliyuncs.com/static/image/thumbnails_preview.png" class="zoom-custom-imgs" alt="Video thumbnail" />

:::




### Generate thumbnails (FFmpeg)

Use [FFmpeg](http://ffmpeg.org/)Processing video is a good choice, here we use it to generate video thumbnails. The following command can create a video thumbnail with scale=160:90 and tile=10x10:

```sh
ffmpeg -i video.mp4 -vsync vfr -vf "select=isnan(prev_selected_t)+gte(t-prev_selected_t\,1),scale=160:90,tile=10x10" -qscale:v 3 "output%03d.jpg"
```



### Configuration

| Attribute name     | Types of | Defaults | Description                                                  |
| ------------------ | -------- | -------- | ------------------------------------------------------------ |
| thumbnails         | Object   | {}       |                                                              |
| thumbnails.preview | Array    | []       | Thumbnail configuration list, accepts resource addresses of multiple thumbnails arranged in order |
| thumbnails.tile    | Array    | [10,10]  | Specify thumbnail arrangement rules                          |
| thumbnails.scale   | Array    | [160,90] | Specify the  default size of the video thumbnail image : [160,90], which means width = 160px, height = 90px; |



### Use thumbnail

MuiPlayer does not limit the thumbnail size to a specified size, but you need to specify the thumbnail size. The scale parameter specifies the aspect ratio, and the tile parameter specifies the arrangement rules of the thumbnail fragments.

```javascript
let thumbnails = {
    preview:['./image/thumbnail001.jpg','./image/thumbnail002.jpg'], // Thumbnail configuration address
    tile:[10,10], // Thumbnail arrangement rules
    scale:[160,90], // Thumbnail image aspect ratio
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

- [Reference One](https://www.bogotobogo.com/FFMpeg/ffmpeg_select_scene_change_keyframes_tile_Creating_a_mosaic_of_screenshots_from_a_movie.php)
- [Reference two](https://superuser.com/questions/538112/meaningful-thumbnails-for-a-video-using-ffmpeg)
- [Reference Three](https://askubuntu.com/questions/377579/how-can-i-use-ffmpeg-to-output-a-screenshot-gallery-mosaic)