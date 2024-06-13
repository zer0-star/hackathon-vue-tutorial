<script setup lang="ts">
import { defineProps } from 'vue'

const props = defineProps<{
  id: number
  count: number
  time: Date
}>()
</script>

<template>
  <v-card width="300" elevation="4">
    <v-card-title>Snapshot #{{ props.id }}</v-card-title>
    <v-card-text>
      <v-list>
        <v-list-item>count: {{ props.count }}</v-list-item>
        <v-list-item>time: {{ props.time.toLocaleString('ja-JP') }}</v-list-item>
      </v-list>
    </v-card-text>
  </v-card>
</template>
