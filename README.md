#调用
<link type="text/css" rel="stylesheet" href="https://video3-naya.vercel.app/ckplayer/css/ckplayer.css" />
<script type="text/javascript" src="https://video3-naya.vercel.app/ckplayer/js/ckplayer.js" charset="UTF-8"></script>
<div class="video" style="width: 100%;height: 100%;">播放器容器</div>
<script type="text/javascript">
    //定义一个变量：videoObject，用来做为视频初始化配置
    var videoObject = {
        container: '.video', //“#”代表容器的ID，“.”或“”代表容器的class
        video: ''//视频地址
    };
    var player = new ckplayer(videoObject);//初始化播放器
</script>
