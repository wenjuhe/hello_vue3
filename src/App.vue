//.vue文件中能写什么?  三个标签 template script style


<template>
  <Person/>
</template>


<script lang="ts">
  import Person from './components/Person5.vue'

  export default {
    name: 'App', //组件名
    components:{Person} //注册组件
  }
</script>

