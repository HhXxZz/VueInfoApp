<style>
  .mu-menu-item{
    width: 120px;
  }
</style>

<template>
  <div>
  <mu-appbar title="Title">
    <mu-icon-button icon='menu' slot="left" @click="openDraw"/>
    <mu-icon-menu icon="more_vert" slot="right">
      <mu-menu-item class="mu-menu-item" title="夜间模式"/>
      <mu-menu-item class="mu-menu-item" title="设置选项"/>
    </mu-icon-menu>
  </mu-appbar>
</div>
</template>

<script>
export default {
  name: 'index',
  data () {
    return {

    }
  },
  methods:{
    openDraw(){
      this.$parent.toggle(true)
    }
  }
}
</script>
