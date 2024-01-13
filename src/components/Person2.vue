<template>
    <div class="person2">
        <h2>姓名:{{ name }}</h2>
        <h2>年龄:{{ age }},{{ nl }}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
    </div>
</template>


<script lang="ts" setup name="Person2">
    import {reactive,toRefs,toRef} from 'vue'
    let person = reactive({
        name:'张三',
        age:18,
    })

    //解构赋值
    let {name,age} = toRefs(person)
    console.log(toRefs(person))
    console.log(name)
    console.log(age)
    console.log('***')

    let nl = toRef(person,'age')
    console.log(nl,nl.value)


    console.log(name,age)

    function changeName() {
        name.value += '~'
        console.log(name.value,person.name)
    }

    function changeAge() {
        age.value += 1
        console.log(age.value,person.age)
    }

</script>

<style scoped>
    .person2 {
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