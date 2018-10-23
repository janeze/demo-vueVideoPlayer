### vue-video-player
----------
视频播放插件

----------
#### 如何使用？
最基础，最少配置用法：
template:
``` htmlbars
 <video-player class="vjs-big-play-centered "
        :options="playerOptions"></video-player>
```
script:
``` javascript
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
```
####主题配置
- vjs-big-play-centered ：设置播放按钮在中间位置，默认在左上角
####常用属性配置
1. width 设置宽度（String or Number）如 375 或者 '375px' 
2. height 设置高度（String or Number）
3. fluid 设置播放器适应容器大小（true or false）
4. aspectRatio 设置播放器宽高比 （String） 如 '16:9'
5. sources 设置播放源 , 数组类型，数组元素为对象类型，对象属性如下
  - type 播放类型
  - src 视频链接    
如：[{
          type: 'video/mp4',
          src: 'http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4'
        }]
6. playbackRates 设置播放倍数 如：[0.7, 1.0, 1.5, 2.0]
7. muted 是否静音（true or false）
8. autoplay 是否自动播放（true or false）
9. loop 是否重复播放（true or false）
10. poster 视频略缩图url (String)
11. preload 设置预加载项 
   'auto':立即开始加载视频，某些设备为了节省用户宽带不会预加载;
   'metadata':仅加载视频的元数据，其中包括视频的持续时间和尺寸等信息。有时，元数 据将通过下载几帧视频来加载;
   'none':不要预加载任何数据。浏览器将等待用户点击“播放”开始下载。
12. notSupportedMessage 无法播放媒体源时显示的默认消息。（String）
####功能组件控制 
对功能树组件的控制可实现性能优化的目的，一般的，设置为false ，对应节点将不在页面节点中存在，从而减少dom节点，达到性能优化目的.（true or false）
1. bigPlayButton 控制是否添加播放按钮，设置为false时，默认点击画面就播放 （true or false）
2. posterImage 控制是否添加视频略缩图，设置为false时，poster选项将不起作用
3. errorDisplay 控制是否添加错误信息显示的选项，设置为false时，notSupportedMessage选项将不起作用
4. loadingSpinner 正在加载视频的动画，当网络较慢的时候方便查看效果
5. bigPlayButton 控制是否添播放按钮，设置为false时，默认点击画面就播放视频
6. textTrackDisplay 控制字幕显示
7. controlBar ：控制条组件配置 , 对象类型
   1. playToggle 是否添加播放按钮 
   2. fullscreenToggle 全屏显示按钮
   3.  currentTimeDisplay 已播放时长
   4.   timeDivider 播放时长分割线
   5.  durationDisplay 视频时长
   6.  remainingTimeDisplay 剩余播放时长
   7.   progressControl 进度条
   8.  muteToggle 静音按钮
####常用事件
- ready 准备好
- play 播放
- pause 暂停
- statechanged 播放进度改变
####常见问题

####参考
https://github.com/surmon-china/vue-video-player
https://github.com/videojs/video.js
https://docs.videojs.com/
http://coderlt.coding.me/2016/02/26/videojs-readme/
https://blog.csdn.net/qianqianyixiao1/article/details/50732050