//.vue文件中能写什么?  三个标签 template script style


<template>
    <div class="app">
        <h1>你好</h1>
    </div>
</template>


<script lang="ts">
  export default {
    name: 'App' //组件名
  }
</script>

<style>
/* 样式 */
  .app {
    background-color: #ddd;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
  }
</style>