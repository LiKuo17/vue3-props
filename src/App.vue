<template>

  <div>
    <div>父组件</div>
    <HelloWorld title="测试hooks" a="lilili" ref="Hello" @on-click="getName" :value="a"></HelloWorld>
    <button @click="accept">接收</button>
  </div>

</template>

<script setup lang='ts'>
import { ref,reactive } from 'vue'
import HelloWorld from './components/HelloWorld.vue';

const Hello = ref<InstanceType<typeof HelloWorld>>()

const a = ref('父组件传过来的')
const getName =(value:String) =>{
  console.log(value);
  
}


const accept = () => {
  console.log(Hello.value?.name,Hello.value?.open);
}
</script>
<style scoped lang='less'>

</style>