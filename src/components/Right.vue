<template>
<div class="right">
  <div>Right组件</div>
  <div>来自子组件的值{{countFromSon}}</div>
  <MyCount @numchange="getNumCount" :init="2"></MyCount>
</div>
</template>

<script>
export default {
  name: "Right",
  data(){
    return{
      countFromSon:0
    }
  },
  methods:{
    getNumCount(val){
      this.countFromSon = val;
    }
  }
}
</script>

<style lang="less">
div.right{
  height: 200px;
  width: 50%;
  background: blue;
  float:right;
}
div.count{
  color: #2f2712;
}
</style>