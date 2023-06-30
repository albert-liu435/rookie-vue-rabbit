<script setup>
import { ref } from "vue";


//defineExpose()
//默认情况下在<script setup>语法糖下组件内部的属性和方法是不开放给父组件访问的，可以通过defineExpose编译宏指定哪些属性和方法允许访问



const name = ref('test name')
const setName = () => {
  name.value = "test new name"
}
defineExpose({
  name,
  setName
})

</script>

<template>
  <div>
    我是test组件
  </div>
</template>



<style lang="scss">
</style>