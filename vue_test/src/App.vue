<template>
 <div>
  <button @click="myFun">改变祖级</button> 祖级：{{ name.name }}
 </div>
  <HelloWorld/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import {provide , reactive} from 'vue'

export default {
   setup(){
     let name =  reactive({name:'000'})
     provide('myName',name) // 1.名字 ，2.数据 ，给后代提供名为name的数据
     function myFun(){
      name.name = '999'
     }
     return {
      name,myFun
     }
  },
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
