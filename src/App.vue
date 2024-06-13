<script setup lang="ts">
import { ref, type Ref } from 'vue'

import SnapshotItem from './SnapshotItem.vue'

const count = ref(0)
const id = ref(1)
const snapshots: Ref<{ id: number; count: number; time: Date }[]> = ref([])

const addSnapshot = () => {
  snapshots.value.unshift({
    id: id.value,
    count: count.value,
    time: new Date()
  })

  id.value++
}
</script>

<template>
  <main :class="$style.main">
    <v-card width="300" elevation="4">
      <v-card-text>
        <div :class="$style.text">count = {{ count }}</div>
      </v-card-text>
      <v-card-actions>
        <v-btn variant="tonal" density="comfortable" @click="count++">+1</v-btn>
        <v-btn variant="tonal" density="comfortable" @click="count--">-1</v-btn>
        <v-btn variant="tonal" density="comfortable" @click="addSnapshot">new snapshot</v-btn>
      </v-card-actions>
    </v-card>
    <div :class="$style.snapshots">
      <snapshot-item v-for="snapshot in snapshots" :key="snapshot.id" v-bind="snapshot" />
    </div>
  </main>
</template>

<style module>
.main {
  width: 100%;
  padding: 20px;
  display: flex;
  justify-content: center;
  align-items: start;
  flex-direction: row;
  font-size: 24px;
  gap: 8px;
}

.text {
  font-size: 24px;
}

.snapshots {
  display: flex;
  flex-direction: column;
}
</style>
