<style lang="css">
.my-swipe {
  position:relative;
  height: 650px;
  color: #ff0;
  font-size: 30px;
  text-align: center;
}

.slide-item {
  position: relative;
  height: 150px;
  background-color: #0089dc;
  color: #ff0;

}
.slide-item img{
  width: 100%;
  height: 280px;
}
.slide-item span{
  position: absolute;
  width: 90%;
  height: auto;
  bottom:30px;
  left: 5%;
  color: #fff;
  font-size: 20px;
  font-weight:bold;
  text-align: left;
}
</style>
<template>
	<swipe :speed="500" :auto="0" :show-indicators="true" class="my-swipe">
	  <swipe-item class="slide-item" v-for="item in sliderList">
	  	<img :src="item.imgUrl" />
      <span>{{item.title}}</span>
	  </swipe-item>
	  
	</swipe>
</template>

<script>
require('vue-swipe/dist/vue-swipe.css');
import { Swipe, SwipeItem } from 'vue-swipe'
export default {
  name: 'slider',
  data () {
    return {
      sliderList:[
      	{
      		id:'',
      		title:'全身心地为另一半而活，终究会埋葬自己',
      		imgUrl:'http://img06.tooopen.com/images/20160924/tooopen_sy_179893728711.jpg'
      	},
      	{
      		id:'',
      		title:'害怕谈钱伤感情的人，可能都不懂钱',
      		imgUrl:'http://img02.tooopen.com/images/20160509/tooopen_sy_162010226417.jpg'
      	},
      	{
      		id:'',
      		title:'地震完不光有直接损失，钱还贬值了……',
      		imgUrl:'http://img02.tooopen.com/images/20160128/tooopen_sy_155637192419.jpg'
      	}
      	]
    }
  },
  components:{
      Swipe,
      SwipeItem
  },
  methods:{
    	
  }
}
</script>