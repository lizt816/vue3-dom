<template>
 <div>
  孙子接受：{{ name }}
 </div>
</template>

<script setup>
import { inject } from 'vue'
let name =  inject('myName')
console.log(name)
</script>
<style scoped>
</style>
