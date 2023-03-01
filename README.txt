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
