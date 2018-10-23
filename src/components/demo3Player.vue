<template>
    <video-player class="vjs-big-play-centered "
        :options="playerOptions"
        ref="videoPlayer"
        @ready="playerReadied"
        @play="onPlayerPlay"
        @pause="onPlayerPause"
        @statechanged="playerStateChanged"
    ></video-player>
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
  mounted () {
    console.log('this is current player instance object', this.player)
  },
  computed: {
    player () {
      return this.$refs.videoPlayer.player
    }
  },
  methods: {
    // 视频已准备好
    playerReadied (player) {
      console.log('the player is readied', player)
      // you can use it to do something...
      // player.[methods]
    },
    // 开始播放
    onPlayerPlay (player) {
      console.log('player play!', player)
    },
    // 暂停播放
    onPlayerPause (player) {
      console.log('player pause!', player)
    },
    // 播放进度改变
    playerStateChanged (playerCurrentState) {
      // console.log('player current update state', playerCurrentState)
    }
  }
}
</script>
