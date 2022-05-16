<template>
<div>
    <span>TestVue组件</span>
    <div>获取数据</div>
    <div>
        <div>共有{{category.length}}个分类</div>
        <div v-for="c in category">
            <span>{{c.name}}</span>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name:"Test",
    props:{
        init:{
            default:0,
            type:Number
        }
    },
    data(){
        return{
            msg:"hello",
            url:"http://longy.ltd:8080/shop/categories",
            category:[]
        }
    },
    methods:{
        show(){
            console.log("hello world");
        },
        getCategory(){
            const xhr = new XMLHttpRequest();
            xhr.addEventListener("load", ()=>{
                let result = JSON.parse(xhr.responseText);
                this.category = result.content;
                console.log(this)
            });
            xhr.open("get", this.url);
            xhr.send();
        }
    },
    beforeCreate(){
        //创建生命周期函数 没啥用，什么做不了
    },
    created(){
        //数据初始化已成功，但模板结构没有生成
        console.log(this.init);
        console.log(this.msg);
        this.show();
        //通过axios获取数据
        this.getCategory();
    },
    mounted(){
         
    }
}
</script>

<style scoped lang="less">

</style>