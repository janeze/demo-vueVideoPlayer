<template>
    <video-player class="vjs-big-play-centered "
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
        sources: [{
          type: 'video/mp4',
          src: 'http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4'
        }]
      }
    }
  },
  methods: {
  }
}
</script>
