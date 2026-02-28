<script setup>
import Header from "@/components/Header.vue";
import Card from "@/components/Card.vue";

const currentDate = new Date();
</script>

<template>
  <Header />

  <Card
      number="1"
      word="test"
      translate="Тест"
  />
</template>

<style scoped>
</style>
