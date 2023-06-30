
<script setup>
//- 侦听单个数据
import { ref, watch } from 'vue';
const state = ref({ name: "abc", age: 18 });

const changeName = () => {
  //直接修改name
  state.value.name = 'cba';
};

const changeAge = () => {
  //直接修改name
  state.value.age++;
};

//精确侦听对象的某个属性

//需求：在不开启deep的前提下，侦听age的变化，只有age变化时才执行回调
watch(() => state.value.age, () => {
  console.log('age变化了')
})

</script>

<template>
  <div>当前name--{{ state.name }}</div>
  <div>当前age-- {{ state.age }}</div>
  <div>
    <button @click="changeName">修改name</button>
    <button @click="changeAge">修改age</button>
  </div>
</template>