<template>
    <video-player class="vjs-custom-skin vjs-big-play-centered"
        :options="playerOptions"></video-player>
</template>

<script>
import 'video.js/dist/video-js.css'
import {videoPlayer} from 'vue-video-player'
export default {
  components: {
    videoPlayer
  },
  data () {
    return {
      playerOptions: {
        fluid: true, // 播放器适应容器大小
        aspectRatio: '16:9', // 播放器宽高比
        // width: 375, // 视频宽度,数字类型或者字符串，单位为px
        // height: 360, // 视频高度数字类型或者字符串，单位为px
        // 属性设置为false则不添加节点，对应节点在页面中将不存在
        playbackRates: false, // 播放倍数[0.7, 1.0, 1.5, 2.0]
        muted: false, // 是否静音
        autoplay: false, // 是否自动播放
        loop: false, // 是否重复播放
        poster: 'http://img.hb.aicdn.com/409467ed2fa5292b83fe954a840e27cf9bbf29b489286-YnjZ67_fw658', // 视频播放前（第一帧）显示的画面url
        preload: 'auto', // 'auto':立即开始加载视频，某些设备为了节省用户宽带不会预加载;'metadata':仅加载视频的元数据，其中包括视频的持续时间和尺寸等信息。有时，元数据将通过下载几帧视频来加载;'none':不要预加载任何数据。浏览器将等待用户点击“播放”开始下载。
        notSupportedMessage: '此视频暂无法播放，请稍后再试', // 无法播放媒体源时显示的默认消息。
        sources: [{
          type: 'video/mp4',
          src: 'http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4'
        }],
        techOrder: ['html5'], //, 'flash'], // 设置优先使用html5播放
        textTrackDisplay: false, // 字幕
        posterImage: true, // 略缩图--poster设置的图片将失效
        errorDisplay: false, // 错误信息显示
        loadingSpinner: true, // 正在加载中的动画
        bigPlayButton: true, // 播放按钮显示
        controlBar: {
          playToggle: true, // 播放按钮
          fullscreenToggle: true, // 全屏显示
          currentTimeDisplay: true, // 已播放时长
          timeDivider: true, // 时间分隔线
          durationDisplay: true, // 视频时长
          remainingTimeDisplay: false, // 剩余播放时长
          progressControl: {
            seekBar: { // 拖动条和进度条的容器
              loadProgressBar: true, // 加载进度显示
              playProgressBar: true // 播放指针显示
              // seekHandle: function (e) {
              //   console.log(e)
              // }
            }
          }, // 进度条
          // volumeControl: { // 音量控制条
          //   volumeBar: {
          //     volumeLevel: '',
          //     // volumeHandle: function () {}
          //   }
          // },
          muteToggle: false // 隐藏静音按钮
        }
      }
    }
  },
  methods: {
  }
}
</script>
<style type="text/css">
.vjs-custom-skin > .video-js .vjs-time-control,
.vjs-custom-skin > .vjs-no-flex .vjs-time-control {
  min-width: 1em;
  padding: 0;
  margin: 0 .1em;
  text-align: center;
  display: block;
}
</style>
