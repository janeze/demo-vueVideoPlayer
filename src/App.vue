<template>
  <ol class="root">
    <li class="ui-item">
      <p>简单用法</p>
      <ol>
        <li>设置播放视频路径</li>
        <li>设置播放器大小（固定或者适应容器大小）、比例</li>
      </ol>
      <demo1-player></demo1-player>
    </li>
    <li class="ui-item">
      <p>常用属性配置</p>
      <ol>
        <LI>设置略缩图</LI>
        <li>设置视频源</li>
        <li>设置宽度自适应</li>
        <li>设置显示播放按钮</li>
        <li>设置显示音量</li>
        <li>设置显示播放进度条</li>
        <li>设置显示播放进度比例</li>
        <li>设置允许全屏</li>
        <li>除了上述组件，不添加其他组件</li>
      </ol>
      <demo2-player></demo2-player>
    </li>
    <li class="ui-item">
      <p>事件</p>
      <ol>
      </ol>
      <demo3-player></demo3-player>
    </li>
  </ol>
</template>

<script>
import demo1Player from './components/demo1Player'
import demo2Player from './components/demo2Player'
import demo3Player from './components/demo3Player'
export default {
  name: 'App',
  components: {
    demo1Player,
    demo2Player,
    demo3Player
  },
  data () {
    return {
    }
  },
  methods: {
  }
}
</script>

<style>
.root{
  width:375px;
  margin:auto;
  padding: 0;
  background: #fefefe;
  list-style-type: korean-hanja-informal;
  list-style-position:inside;
}
.ui-item{
  position: relative;
  margin:8px 0;
  padding:8px 4px;
  border:1px solid #ddd;
  color: #666;
}
.ui-item>p{
  margin:0;
  position: absolute;
  top: 7px;
  left: 40px;
}
</style>
