<script setup>
//<script>
// export default {
//   setup () {
//     console.log('setup', this)
//     //setup选项中写代码的特点
//     const message = 'this is message';
//     //函数
//     const logMessage = () => {
//       console.log(message)
//     }
//     return {
//       message,
//       logMessage
//     }
//   },
//   beforeCreate () {
//     console.log('beforeCreate')
//   }
// }

const message = 'this is message';
const logMessage = () => {
  console.log(message)
};

//reactive()接受对象类型数据的参数传入并返回一个响应式的对象
//1、导入函数
import { reactive, ref } from 'vue';

//2、执行函数，传入一个对象类型的函数，变量接收
const state = reactive({
  count: 0
})
const setCount = () => {
  state.count++;
}
//ref()作用：接收简单类型或者对象类型的数据传入并返回一个响应式的对象
//执行函数，传输参数 建单类型或者对象类型，变量接收
const counta = ref(0)

const setCounta = () => {
  console.log(counta)
  //脚本区域修改ref产生的响应式对象数据，必须通过.value属性
  counta.value++;
}
</script>

<template>
  <div>
    使用数据和方法
    {{message}}
    <button @click="logMessage">log</button>

  </div>
  <div>####################</div>
  <div>
    <button @click="setCount">{{ state.count }}</button>
  </div>
  <div>####################</div>
  <div>
    <button @click="setCounta">{{ counta }}</button>
  </div>
</template>