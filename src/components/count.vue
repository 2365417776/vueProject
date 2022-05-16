<template>
<div>
  <div class="count">计数{{num}}</div>
  <button @click="addNum">点击加1</button>
</div>
</template>

<script>
export default {
  name: "count",
  data:function(){
    return{
      num:this.init
    }
  },
  props: {
    init:{
      default:0,
      type:Number,
      required:true
    }
  },
  methods:{
    addNum(){
      this.num ++;
      this.$emit('numchange', this.num);
    },
  }
}
</script>

<style scoped lang="less">

</style>