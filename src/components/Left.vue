<template>
  <div class="left">
    <div class="title">Left组件</div>
    <div>父组件传递的值是{{msg}}</div>
    <MyCount :init="2"></MyCount>
    <slot name="first">
      <p>我是一个Left插槽</p>
    </slot>
    <slot name="second">

    </slot>
  </div>
</template>

<script>
export default {
  name: "Left",
  //prop是自定义属性
  props:['msg'],
}
</script>

<style scoped lang="less">
div.left{
  height: 200px;
  width: 50%;
  background: #57d943;
  float:left;
}
// 加了scoped父组件可以修改子组件样式
/deep/ div.count{
  color:pink;
}
</style>