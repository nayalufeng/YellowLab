<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>奖励自己</title>
    <link href="https://vjs.zencdn.net/7.4.1/video-js.css" rel="stylesheet">
    <script src='https://vjs.zencdn.net/7.4.1/video.js'></script>
    
    <script src="https://cdnjs.cloudflare.com/ajax/libs/videojs-contrib-hls/5.15.0/videojs-contrib-hls.min.js" type="text/javascript">
    </script>

    <!-- videojs-contrib-hls
     用于在电脑端播放 如果只需手机播放可以不引入 
     -->
</head>
<body>
<style>
    .video-js .vjs-tech {position: relative !important;}
</style>
<div>
    <video id="myVideo" class="video-js vjs-default-skin vjs-big-play-centered" controls  autoplay  data-setup='{}' style='width: 100%;height: auto'>
        <source id="source" src="https://cdn.jsdelivr.net/gh/nayalufeng/yellowlab/cdn//index.m3u8" type="application/x-mpegURL"></source>
    </video>

</body>

<script>
    // videojs 简单使用
    var myVideo = videojs('myVideo', {
        bigPlayButton: true,
        textTrackDisplay: false,
        posterImage: false,
        errorDisplay: false,
    })
    myVideo.play()
    var changeVideo = function (vdoSrc) {
        if (/\.m3u8$/.test(vdoSrc)) { //判断视频源是否是m3u8的格式
            myVideo.src({
                src: vdoSrc,
                type: 'application/x-mpegURL' //在重新添加视频源的时候需要给新的type的值
            })
        } else {
            myVideo.src(vdoSrc)
        }
        myVideo.load();
        myVideo.play();
    }
    var src = '#';
    document.querySelector('.qiehuan').addEventListener('click', function () {
        changeVideo(src);
    })
</script>























--mp4专用--
<link type="text/css" rel="stylesheet" href="https://nayalufeng.github.io/video3/ckplayer/css/ckplayer.css" />
<script type="text/javascript" src="https://nayalufeng.github.io/video3/ckplayer/js/ckplayer.js" charset="UTF-8"></script>
<div class="video" style="width: 100%;height: 100%;">播放器容器</div>
<script type="text/javascript">
    //定义一个变量：videoObject，用来做为视频初始化配置
    var videoObject = {
        container: '.video', //“#”代表容器的ID，“.”或“”代表容器的class
        video: 'https://cdn.jsdelivr.net/gh/nayalufeng/yellowlab/cdn//index.m3u8'//视频地址
    };
    var player = new ckplayer(videoObject);//初始化播放器
</script>
--m3u8专用--
<script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
<video id="video" controls loop="false" width="100%"></video>
<script>
  var video = document.getElementById('video');
  if(Hls.isSupported()) {
  var hls = new Hls();
  hls.loadSource('https://cdn.jsdelivr.net/gh/nayalufeng/yellowlab/cdn//index.m3u8');
  hls.attachMedia(video);
  hls.on(Hls.Events.MANIFEST_PARSED,function() {
  video.play();
});
} else if (video.canPlayType('application/vnd.apple.mpegurl')) {
  video.src = 'https://cdn.jsdelivr.net/gh/nayalufeng/yellowlab/cdn//index.m3u8';
  video.addEventListener('loadedmetadata',function() {
  video.play();
});
}
</script>
