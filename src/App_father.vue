
<script setup>

import { ref } from "vue";
//组合式API下的父子传值
//1、父组件中给子组件绑定属性
//引入子组件
import sonComVue from "./son-com.vue";
//响应式数据
const count = ref(100)

setTimeout(() => {
  count.value++
}, 3000);


const getMessage = (msg) => {
  console.log(msg)
}
</script>

<template>
  <div class="father">
    <h2>父组件App</h2>
    <!-- 1、绑定属性 -->
    <sonComVue :count="count"
               message="father message" />
  </div>
  <div>======================================</div>
  <!-- 1、绑定自定义事件 -->
  <sonComVue @get-Message="getMessage"></sonComVue>
</template>

