<template>
  <div>
<h2>{{inp}}</h2>
    <label for="input">Input: </label>
<input type="text" ref="input" name="input" id="input" v-model.trim="inp"><br>
 
</div>
</template>

<script setup>
import { computed, ref, reactive, onMounted, watchEffect } from "vue";
 const input = ref(null)
 const inp = ref(null)
onMounted(()=>{
  input.value.focus()
})

// watchEffect(()=>{
//   if (input.value) {
//     input.value.focus()
//   }
// })


</script>

<style scoped>

</style>