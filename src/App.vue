<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <main :class="$style.main">
    <v-card min-width="300" elevation="4">
      <v-card-text>
        <div :class="$style.text">count = {{ count }}</div>
      </v-card-text>
      <v-card-actions>
        <v-btn variant="tonal" density="comfortable" @click="count++">+1</v-btn>
        <v-btn variant="tonal" density="comfortable" @click="count--">-1</v-btn>
      </v-card-actions>
    </v-card>
  </main>
</template>

<style module>
.main {
  width: 100%;
  padding: 20px;
  display: grid;
  place-items: center;
  font-size: 24px;
}

.text {
  font-size: 24px;
}
</style>
