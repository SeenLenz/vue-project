<script setup lang="ts">
import Table from '@/components/Table.vue'
import type { Ibook } from '@/models/book'
const props = defineProps<{
  book: Array<Ibook>
}>()
</script>

<template>
  <div class="wrapper">
    <Table :book_params="book"></Table>
  </div>
</template>

<style lang="scss" scoped>
.wrapper {
  display: flex;
  height: 100%;
  padding: 4px;
  border-radius: 8px;
  justify-content: space-evenly;
}
</style>
