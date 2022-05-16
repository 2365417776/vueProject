<template>
  <div class="box">
    <h1>appVUe组件{{username}}</h1>
    <button @click="change">更改用户</button>
    <div style="clear:both"></div>
    <Test></Test>
    <Left :msg="message">
      <template #first>
          <p>Left插槽自定义1</p>
      </template>
      <template #second>
          <p>Left插槽自定义2</p>
      </template>
    </Left>
    <Right></Right>
  </div>
</template>

<script>
// 导入Vue组件
import Left from '@/components/Left'
import Right from '@/components/Right'
import Test from '@/components/Test' 

export default {
  data(){
    return{
      username:"小月",
      message:"hello world"
    }
  },
  methods:{
    change(){
      this.username = "小红"
    }
  },
  components:{
    Left,
    Right,
    Test
}
}
</script>
<style lang="less">
  div.box{
    background: pink;
    h1{
      color:red;
    }
  }
</style>