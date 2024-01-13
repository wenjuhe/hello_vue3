<!-- <template>
    <div class="person">
        //插值语法
        <h2>姓名: {{name}}</h2>
        <h2>年龄: {{age}}</h2>
        <h2>地址: {{address}}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">查看联系方式</button>
    </div>
</template> -->

<template>
    <div class="person">
        <h2>汽车信息: 一辆{{car.brand}}车,价值{{car.price}}万</h2>
        <button @click="changePrice">修改汽车的价格</button>
        <br>
        <h2>游戏列表: </h2>
        <ul>
            <li v-for="g in games"  v-bind:key="g.id">{{ g.name}}</li>
        </ul>
        <button @click="changeFirstGame">修改第一个游戏的名字</button>
        <hr>
        <h2>测试: {{obj.a.b.c}}</h2>
        <button @click="changeObj">测试</button>
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
<!-- <script lang="ts" setup name="Person">
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
</script> -->

<script lang="ts" setup name="person">
    import {reactive} from 'vue'
    //数据
    let car = reactive({brand:'奔驰',price:100})
    let games = reactive([
        {id:'01',name:'王者荣耀'},
        {id:'02',name:'蛋仔派对'},
        {id:'03',name:'QQ飞车'}
    ])
    //深层次的
    let obj = reactive({
        a:{
            b:{
                c:666
            }
        }
    })
    console.log(car)
    //方法
    function changePrice() {
        car.price += 10
    }

    function changeFirstGame() {
        games[0].name = '穿越火线'
    }
    function changeObj(){
        obj.a.b.c = 999
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
  li {
    font-size: 20px;
  }
</style>