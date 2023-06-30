
<script setup>
//声明周期函数使用
//1、导入声明周期函数
import { onMounted, onUnmounted } from 'vue';
//2、执行声明周期函数，传入回调
onMounted(() => {
  //自定义逻辑
  console.log("mount1")
})
onMounted(() => {
  //自定义逻辑
  console.log("mount2")
})
onUnmounted(() => {
  console.log("onUnmounted");
})
</script>

<template>

</template>