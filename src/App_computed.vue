<script setup>
//import { computed } from 'vue';

//computed计算属性函数  计算属性基本思想和Vue2的完全一致，组合式API下的计算属性只是修改了写法

import { ref } from 'vue';

const list = ref([1, 2, 3, 4, 5, 6, 7, 8])

//导入computed
import { computed } from 'vue';
//执行函数return计算之后的值，变量接收
const computedList = computed(() => {
  return list.value.filter(item => item > 2)
})

setTimeout(() => {
  list.value.push(9, 10)
}, 3000);

</script>

<template>
  <div>
    原始响应式数组-{{ list }}
  </div>
  <div>
    计算属性数组-{{ computedList }}
  </div>
</template>