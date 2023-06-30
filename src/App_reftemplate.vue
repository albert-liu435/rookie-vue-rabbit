
<script setup>

import { onMounted, ref } from "vue";
import TestCom from "./test-com.vue";

//模板引用的概念
//通过ref标识获取真实的dom对象或者组件实例对象

//1、调用ref函数->ref对象
const h1Ref = ref(null)
//组件挂载完毕之后才能获取
onMounted(() => {
  console.log(h1Ref.value)
  console.log(comRef.value)
})

//组件实例对象
const comRef = ref(null);
</script>

<template>
  <!-- 2、通过ref标识绑定ref对象 -->
  <h1 ref="h1Ref">我是dom标签h1</h1>
  <TestCom ref="comRef" />
</template>

