<script setup>
</script>

<template>
  <button>
    <slot></slot>
  </button>
</template>

<style scoped>
button {
  border-radius: 100px;
  padding: 16px 10px;
  min-width: 335px;
  background: var(--color-primary);

  font-weight: 400;
  font-style: normal;
  font-size: 24px;
  line-height: 1.5;
  text-align: center;

  color: var(--color-font-light);
  border: none;

  transition: background .3s;

  cursor: pointer;
}

button:hover {
  background: var(--color-primary-hover);
}
</style>