<template>

  <div class="content">
    <div>子组件</div>
    <div>我是子组件</div>
    <div>{{ value }}</div>
    <button type="button" @click="goFather">传值</button>
  </div>
  

</template>

<script setup lang='ts'>
import { ref,reactive, useAttrs } from 'vue'
const props = defineProps({
  value:{
    type:String
  }
})

const attrs = useAttrs()
console.log(attrs);



console.log(props.value);
const name = ref('xiaoli')
const emit = defineEmits(['on-click'])

const goFather = () =>{
  emit('on-click','我是子组件传过去的值')
}


defineExpose({
  name:name,
  open: ()=>{
    console.log('利用暴露Expose传值');
  }
})
</script>
<style scoped lang='less'>
.content{
  width: 400px;
  height: 200px;
  border: 1px solid red;
}
</style>