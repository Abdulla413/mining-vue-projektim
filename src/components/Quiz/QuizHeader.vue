<script setup>
import { state } from "@/stores/quizStore";

</script>

<template>
  <div> Quiz Header 
    <h5>
        {{state.name}}
    </h5>
  </div>
</template>
