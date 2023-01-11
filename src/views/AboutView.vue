
<script setup>
import { useFlash } from "@/composables/useFlash";
import { counter } from "@/stores/counterStore"
let { flash } = useFlash();
</script>

<template>
  <div class="about">
    <h1>This is an about page {{ counter.count }} </h1>
    <button @click="flash('I am working well in About')">Mini Chiking</button>
  </div>
</template>



<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
