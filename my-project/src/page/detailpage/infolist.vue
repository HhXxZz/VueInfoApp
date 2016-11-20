<template>
<div class="demo-infinite-container">
<mu-refresh-control :refreshing="refreshing" :trigger="trigger" @refresh="refresh"/>

<div class="slider-div">
<slider></slider>
</div>
  <mu-list>
    <template v-for="item in list">
      <mu-list-item class="list-item-sty">
      	<div class="title">到死so撒到i大司空觉得好累阿萨德金卡{{item}}</div>
      	<img src="~assets/logo.png" />
      </mu-list-item>
    </template>
  </mu-list>
  <mu-infinite-scroll :scroller="scroller" :loading="loading" @load="loadMore"/>
</div>
</template>


<script>
import slider from './slider'
export default {
  data () {
    const list = []
    for (let i = 0; i < 15; i++) {
      list.push('item' + (i + 1))
    }
    return {
      list,
      num: 10,
      loading: false,
      scroller: null,
      refreshing: false,
      trigger: null
    }
  },
  mounted () {
    this.scroller = this.$el
     this.trigger = this.$el
  },
  components:{
      slider,
  },
  methods: {
  	refresh () {
      this.refreshing = true
      setTimeout(() => {
        const list = []
        for (let i = this.num; i < this.num + 10; i++) {
          list.push('item' + (i + 1))
        }
        this.list = list
        this.num += 10
        this.refreshing = false
      }, 2000)
    },
    loadMore () {
      this.loading = true
      setTimeout(() => {
        for (let i = this.num; i < this.num + 10; i++) {
          this.list.push('item' + (i + 1))
        }
        this.num += 10
        this.loading = false
      }, 2000)
    }
  }
}
</script>

<style lang="css">
.demo-infinite-container{
  width: 100%;
  height: 100%;
  overflow: auto;
  -webkit-overflow-scrolling: touch;
  border: 1px solid #d9d9d9;
  position: relative;
  user-select: none;
}
.list-item-sty{
	width: 96%;
	height: auto;
	margin-left: 2%;
	margin-bottom: 10px;
	border: 1px solid #ccc;
	-moz-box-shadow: 0 0 2px #ccc; /* 老的 Firefox */
	box-shadow: 0 0 2px #ccc;
	border-radius: 5px;
	background-color: #fff;
}
.list-item-sty .title{
	width: 70%;
	height: 80%;
	float: left;
	font-size: 18px;
	font-style: bold;
}
.list-item-sty img{
	width: 80px;
	height: 60px;
	float: right;
}
.slider-div{
	width: 100%;
	height: 280px;
	float: left;
	margin-top: -20px;
}
</style>