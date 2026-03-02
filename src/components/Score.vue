<script setup>
import HeartIcon from "@/components/icons/HeartIcon.vue";

defineProps({
  score: {
    type: Number,
    default: 0
  }
})
</script>

<template>
<div class="score-block">
  <div class="score-value">{{ score }}</div>
  <HeartIcon />
</div>
</template>

<style scoped>
.score-block {
  display: flex;
  align-items: center;
  gap: 10px;
  border-radius: 36px;
  padding: 12px 24px;
  background: var(--color-primary-light);
  box-shadow: 0 0 4px 0 rgba(0, 0, 0, .15);
}

.score-value {
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  text-align: center;
  color: var(--color-primary);
}

</style>