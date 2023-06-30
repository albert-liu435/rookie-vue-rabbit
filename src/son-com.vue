
<script setup>
//通过definProps "编译器宏" 接收子组件传递的数据
const props = defineProps({
  message: String,
  count: Number
})
console.log(props)

//2、通过defineEmits编译器宏生成emit方法
const emit = defineEmits(['get-message'])
const sendMsg = () => {
  //3、触发自定义事件，并传递参数
  emit('get-message', 'this is son msg')
}
</script>



<template>
  <div class="son">
    <h3>子组件Son</h3>
    <div>
      父组件传入的数据-- {{ message }}--{{ count }}
    </div>
    <div>++++++++++++++++</div>
    <button @click="sendMsg">sendMsg</button>

  </div>
</template>

