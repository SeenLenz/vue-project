<script setup lang="ts">
import type { Ibook } from '@/models/book'

// export interface Ibook {
//   author: string
//   title: string
//   description: string
//   img_url: string
// }

const props = defineProps<{
  book_params: Array<Ibook>
}>()
</script>

<template>
  <table>
    <thead>
      <tr>
        <th v-for="(value, key) in book_params[0]">{{ key }}</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="book in props.book_params">
        <td>{{ book.author }}</td>
        <td>{{ book.title }}</td>
        <td>{{ book.description }}</td>
        <td>
          <img :src="book.img_url" :alt="book.title" />
        </td>
      </tr>
    </tbody>
  </table>
</template>

<style lang="scss" scoped>
table {
  width: 100%;
  border-collapse: collapse;
  font-size: 16px;
  text-align: left;

  td,
  th {
    padding: 8px;
  }

  th {
    background-color: #838383;
    font-weight: bold;
  }

  tr:nth-child(even) {
    background-color: #c2c2c2;
  }

  tr:nth-child(even) {
    background-color: #666666;
  }

  tr:hover {
    background-color: #dddddd;
    transition: all 0.2s ease-out;
  }

  img {
    max-width: 100px;
    height: auto;
    display: block;
  }
}
</style>
