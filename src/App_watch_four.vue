
<script setup>
//- 侦听单个数据
import { ref, watch } from 'vue';
const state = ref({ count: 0 });

const changeStateByCount = () => {
  //直接修改count
  state.value.count++;
};

//watch深度监听
watch(state, () => {
  console.log('count变化了')
},{
  deep:true
})

</script>

<template>
  <div>
    {{ state.count }}
    <button @click="changeStateByCount">通过count修改</button>
  </div>
</template>