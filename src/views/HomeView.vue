<script setup>
import QuizVue from "@/components/Quiz/QuizVue.vue";
import { state } from "@/stores/quizStore";
</script>

<template>
  <main>
    <QuizVue :quiz="state" />
  </main>
</template>
