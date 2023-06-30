<script setup>
//- 侦听单个数据
import { ref, watch } from 'vue';
const count = ref(0);
const name = ref('cp')

const changeCount = () => {
  count.value++;
};

const changeName = () => {
  name.value = 'pc';
};
// //调用watch侦听单个数据源变化
// watch(count, (newValue, oldValue) => {
//   console.log(`count发生了变化了，老值为${oldValue},新值为${newValue}`)
// })

//调用watch侦听多个数据源变化
watch([count, name], ([newCount, newName], [oldCount, oldName]) => {
  console.log('count或者name变化了', [newCount, newName], [oldCount, oldName])
})
</script>

<template>
  <div>
    <button @click="changeCount">修改count--{{ count }}</button>
  </div>
  <div>
    <button @click="changeName">修改name--{{ name }}</button>
  </div>
</template>

