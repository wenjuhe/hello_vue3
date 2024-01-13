//.vue文件中能写什么?  三个标签 template script style


<template>
  <Person2/>
</template>


<script lang="ts">
  import Person2 from './components/Person2.vue'

  export default {
    name: 'App', //组件名
    components:{Person2} //注册组件
  }
</script>

