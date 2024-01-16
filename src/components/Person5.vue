<template> 
    <div class="person5">
        <h1>情况二: 监视【ref】定义的【对象类型】数据</h1>
        <h2>姓名: {{ person.name }}</h2>
        <h2>年龄: {{ person.age }}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="changePerson">修改整个人</button>
    </div>
</template>

<script lang="ts" setup name="Person5">
    import {ref,watch} from 'vue'
    //数据
    let person = ref ({
        name : '张三',
        age : 18
    })

    function changeName() {
        person.value.name += '~'
    }

    function changeAge() {
        person.value.age += 1
    }

    function changePerson() {
        person.value = {name:'李四', age:90}
    }

    //监视 情况一: 监视【ref】定义的【对象类型】数据, 监视的是对象的【地址值】, 若想监视对象内部属性的变化,需要手动开启【深度监视】
    //watch的第一个参数: 被监视的数据
    //watch的第二个参数: 监视的回调
    //watch的第三个参数: 配置对象(deep,immediate等等)
    //注意: 若修改的是ref定义的对象中的属性, newValue 和 oldValue 都是新值，因为它们是同一个对象
    //若修改整个 ref 定义的对象，newValue 是新值，oldValue 是旧值，因为不是同一个对象了

    watch(person,(newValue,oldValue)=>{
        console.log('person变化了',newValue,oldValue)
    },{deep:true,immediate:true})
</script>

<style>
    .person5 {
    background-color: skyblue;
    box-shadow: 0 0 5px;
    border-radius: 10px;
    padding: 20px;
  }
  button {
    margin: 0 10px;
  }
  li {
    font-size: 50px;
  }
</style>