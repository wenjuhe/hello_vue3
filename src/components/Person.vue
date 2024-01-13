<template>
    <div class="person">
        //插值语法
        <h2>姓名: {{name}}</h2>
        <h2>年龄: {{age}}</h2>
        <h2>地址: {{address}}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">查看联系方式</button>
    </div>
</template>

//配置组件名字
<!-- <script lang="ts">
    export default {
        name: 'Person234',
        //vue3在setup中没有维护this
        // setup(){
        //     //console.log('@@',this) setup函数中的this是undefined, Vue3中已经开始弱化this了
        //     //数据 原来是写在data中的, 此时的name age tel都不是响应式的数据
        //     let name = '张三' //注意此时的name不是响应式的
        //     let age = 18
        //     let tel = '12345679'
        //     //方法
        //     function changeName() {
        //         name = 'zhang-san' //注意: 这样修改name, 页面是没有变化的.
        //         console.log(name) //name确实改了,但是name不是响应式的.
        //     }
        //     function changeAge() {
        //         age += 1
        //         console.log(age)
        //     }
        //     function showTel() {
        //         alert(tel)
        //         console.log(tel)
        //     }
        //     return {name,age,changeName,changeAge,showTel}
        //     // return function(){
        //     //     return '哈哈'
        //     // }
        //     // return ()=>{
        //     //     return '哈哈'
        //     // }
        //     //箭头函数 setup的返回值也可以是一个渲染函数
        //     //return ()=> '哈哈'
        // }
    }
</script> -->


//配置组合式api
<script lang="ts" setup name="Person">
    import {ref} from 'vue'
    let name = ref('张三')
    let age = ref(18)
    let tel = '234'
    let address = '北京昌平区宏福苑'

    console.log(1,name)
    console.log(2,age)
    console.log(3,tel)
    console.log(4,address)

    function changeName() {
        name.value = 'zhang-san'
    }
    function changeAge() {
        age.value += 1
    }
    function showTel() {
        alert(tel)
    }
</script>


<style scoped>
    .person {
    background-color: skyblue;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
  }
  button {
    margin: 0 5px;
  }
</style>