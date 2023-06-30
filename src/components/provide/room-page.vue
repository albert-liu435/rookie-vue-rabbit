<script setup>
import { provide, ref } from "vue";
import RoomMsgItem from "./room-msg-item.vue";

//组件嵌套关系：
//RoomPage->RoomMsgItem->roomMsgComment

//1、顶层组件提供数据
provide('data-key', 'this is room data')

const count = ref(0)

setTimeout(() => {
  count.value = 100
}, 3000);
//跨层传递性响应数据
provide('count-key', count)

//跨层传递方法
const setCount = () => {
  count.value++
}

provide('setCount-key', setCount)
</script>

<template>
  <div class="page">
    顶层组件
    <RoomMsgItem />

  </div>
</template>