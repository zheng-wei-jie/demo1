<template>
  <RouterView></RouterView>
</template>
<script setup >
  const a=ref(10)
  const data=computed(()=>{
    return a.value*2
  })
  const fn1 =()=>{
    a.value+=5
  }
  watch(a,(nv,ov)=>{
    console.log('nv',nv);
  })
useHead({
  title: '飞天大盗',
  meta: [
    { name: '王霸天', content: '吊炸天' }
  ],
  bodyAttrs: {
    class: 'test'
  },
  script: [ { innerHTML: 'console.log(\'Hello world\')' } ]
})

  
</script>
<style>

  @import url('element-plus/dist/index.css');


</style>
