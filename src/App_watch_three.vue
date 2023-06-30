
<script setup>
//- 侦听单个数据
import { ref, watch } from 'vue';
const count = ref(0);
const name = ref('cp')

const changeCount = () => {
  count.value++;
};

//watch立即执行
//说明：在侦听器创建时立即触发回调, 响应式数据变化之后继续执行回调
watch(count, () => {
  console.log('count发生了变化')
}, {
  immediate: true
})

</script>

<template>
  <div>
    <button @click="changeCount">+{{ count }}</button>
  </div>
</template>