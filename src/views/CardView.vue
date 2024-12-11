<script setup lang="ts">
import Card from '@/components/Card.vue'
import type { Ibook } from '@/models/book'
const props = defineProps<{
  book: Array<Ibook>
}>()
</script>

<template>
  <div class="wrapper">
    <Card v-for="item in props.book" :book_params="item"></Card>
  </div>
</template>

<style lang="scss" scoped>
.wrapper {
  display: flex;
  height: 100%;
  padding: 4px;
  border-radius: 8px;
  overflow: hidden;
  flex: 1 1 auto;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
</style>
