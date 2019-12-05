<template>
  <view class="body">
  <div @click="toDetail(item.id)" v-for="(item,index) in list" :key="index">
    <image :src="item.iconUrl"></image>
    <text>{{item.title}}</text>
  </div>
</view>
</template>

<script>
const list = require('../../../static/data/lol_duowan.js')
export default {
data() {
  return {
    list:list
  }
},
methods: {
  toDetail(val){
    wx.navigateTo({ url: `../detail/main?id=${val}` });
  }
},
}
</script>

<style>
.body{
  background-color: #566a78;
  padding: 10px;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
.body div{
  margin-bottom: 4px;
  flex: 0 0 33%;
}
image{
  width: 88px;
  height: 88px;
  display: block;
  margin: 0 auto;
}
text{
  display: block;
  text-align: center;
}
</style>