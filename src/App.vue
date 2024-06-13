<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <main :class="$style.main">
    <div>
      <button :class="$style.button" @click="count++">+1</button>
      <button :class="$style.button" @click="count--">-1</button>
    </div>
    <div>count = {{ count }}</div>
  </main>
</template>

<style module>
.main {
  display: flex;
  flex-direction: column;
  font-size: 20px;
}

.button {
  font-size: 20px;
}
</style>
