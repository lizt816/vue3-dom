<template>
  <div id="box">
   {{a}}
  </div>
  <div>
   {{ b }}---{{ ccc }}11
  </div>
  <div>
   {{ c }}
  </div>
  <div>
   {{ d }}
  </div>
  <button @click="changeA">changeA</button>
  <button @click="changeB">changeB</button>
  <button @click="changeD">changeD</button>
  <button @click="keyWord('1454891',2000)">防抖</button>
  <myCompo></myCompo>
</template>

<script setup>
  import myCompo from "./c/myCompo.vue";
  import { ref,reactive,computed,watch,watchEffect,onMounted, toRef} from "vue";

  let ccc = reactive([])
  onMounted(()=>{
    let sss = ''
    sss = document.getElementById('box')
    console.log(sss)
    setTimeout(()=>{
     ccc = ccc.push({name:'111'})
     console.log(ccc,"///")
     // b = Object.assign(b,{name:9999999,age:"8888888"})
     // b = reactive({name:'9999999999999999'})
     b = reactive({name:'333333333333333333333'})
     b = reactive({name:'999'})
    },2000)
    
  })
  let a = ref('111')
  let b ={name:999}
  let c = computed(()=>{
     return b.name+100
   })
  let d = toRef(b.name) 


  // watch和watchEffect ，就和watchEffect和计算属性差不多，不过不需要使用，和watch侦听一样，不过会侦听多个值
  watch(()=>b.name,(n,o)=>{
   console.log(n,o)
  },{immediate:true,deep:true})
  watchEffect(()=>{
     b.name = "222"
  })  
  function changeA() {
   a.value = '*/*-/*-'
  }
  function changeB() {
   b.name = 33
  }
  function changeD() {
   d.value = 888
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
