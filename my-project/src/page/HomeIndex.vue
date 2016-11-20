<style>

  .mu-menu-item{
    width: 120px;
  }
  .list-div{
    width: 100%;
    background-color: #f6f6f6;
  }
</style>

<template>
<div>
<div class="head-class">
  <mu-appbar title="逼乎" :zDepth="5">
    <mu-icon-button icon='menu' slot="left" @click="openDraw"/>
    <mu-icon-menu icon="more_vert" slot="right">
      <mu-menu-item class="mu-menu-item" title="夜间模式"/>
      <mu-menu-item class="mu-menu-item" title="设置选项"/>
    </mu-icon-menu>
  </mu-appbar>
</div>

<div class="list-div" :style="{height:(screenHeight-64)+'px'}">
  <infolist></infolist>
</div>
</div>
</template>

<script>
import infolist from './detailpage/infolist'

export default {
  name: 'index',
  data () {
    return {
      screenHeight:0, //设备屏幕高度
    }
  },
  components:{
      infolist,
  },
  mounted () {
    this.screenHeight = document.documentElement.clientHeight
  },
  methods:{
    openDraw(){
      this.$parent.toggle(true)
    }
  }
}
</script>
