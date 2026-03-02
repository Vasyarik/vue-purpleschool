<script setup>

import Score from "@/components/Score.vue";
</script>

<template>
<header>
  <div class="project-name">ЗАПОМНИ СЛОВО</div>
  <Score />
</header>
</template>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  padding: 50px 60px;
  background: transparent;
}

.project-name {
  font-weight: bold;
  font-size: 16px;
  line-height: 24px;
  letter-spacing: .12rem;
  text-transform: uppercase;
  color: var(--color-font-accent);
}
</style>