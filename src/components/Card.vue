<script setup>
import { ref } from "vue";

defineEmits(['flip', 'status-change'])

const props = defineProps({
  number:    {
    type:    Number,
    default: 1
  },
  word:      {
    type:    String,
    default: ''
  },
  translate: {
    type:    String,
    default: ''
  }
})

const { number } = props;

function formatNumber() {
  return number < 10 ? '0' + number : number;
}
</script>

<template>
  <div class="card">
    <div class="card-inner">
      <div class="card-front">
        <div class="card-content">
          <div class="card-number">{{ formatNumber() }}</div>
          <div class="card-word">{{ word }}</div>
          <div class="card-bottom">ПЕРЕВЕНУТЬ</div>
        </div>
      </div>
      <div class="card-back">
        <div class="card-content">
          <div class="card-number">{{ formatNumber() }}</div>
          <div class="card-word">{{ translate }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  --border-radius: 16px;
  --card-bg: #FFFFFF;
  width: 250px;
  height: 376px;

  perspective: 1000px;
}

.card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

.card:hover .card-inner {
  transform: rotateY(180deg);
}

.card-front,
.card-back {
  width: 100%;
  height: 100%;
  padding: 28px 19px;
  border-radius: var(--border-radius);
  background: var(--card-bg);
  box-shadow: 0 0 16px 0 rgba(0, 0, 0, .10);
  transition: box-shadow .3s;

  position: absolute;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;

  cursor: pointer;
}

.card:hover .card-front,
.card:hover .card-back {
  box-shadow: 0 0 16px 0 rgba(0, 0, 0, .10), 10px 10px 10px 0 rgba(0, 0, 0, .05);
}

.card-back {
  transform: rotateY(180deg);
}

.card-content {
  width: 100%;
  height: 100%;
  border-radius: var(--border-radius);
  border: 1px solid var(--color-primary-light);

  position: relative;

  display: flex;
  justify-content: center;
  align-items: center;
}

.card-number {
  position: absolute;
  top: 0;
  left: 16px;
  transform: translateY(-50%);
  background: var(--card-bg);

  font-weight: 400;
  font-size: 14px;
  line-height: 100%;
  text-align: center;
}

.card-word {
  font-weight: normal;
  font-size: 18px;
  line-height: 100%;
  letter-spacing: 0;
  text-align: center;
}

.card-bottom {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translate(-50%, 50%);
  background: var(--card-bg);

  font-weight: bold;
  font-size: 12px;
  line-height: 18px;
  letter-spacing: .12rem;
  text-transform: uppercase;

  color: var(--color-font-accent);
}
</style>