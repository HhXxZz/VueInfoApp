<style>

</style>
<template>
<div>
<!-- Drawer 抽屉 -->
<div>
<mu-drawer :open="open" :docked="docked" @close="toggle()">
      <mu-list @itemClick="docked ? '' : toggle()">
        <mu-list-item title="Menu Item 1"/>
        <mu-list-item title="Menu Item 2"/>
        <mu-list-item title="Menu Item 3"/>
        <mu-list-item v-if="docked" @click.native="open = false" title="Close"/>
      </mu-list>
</mu-drawer>

<div>
  <home-index></home-index>
</div>

</div>
</template>
<script>
 import homeIndex from './HomeIndex'
export default {
  name: 'home',
  data () {
    return {
      open: false,
      docked: true
    }
  },
  components:{
      homeIndex
  },
  methods:{
    toggle (flag) {
      this.open = !this.open
      this.docked = !flag
    }
  }
}
</script>
