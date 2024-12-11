<script setup lang="ts">
import type { Ibook } from '@/models/book'

// export interface Ibook {
//   author: string
//   title: string
//   description: string
//   img_url: string
// }

const props = defineProps<{
  book_params: Ibook
}>()
</script>

<template>
  <div class="card">
    <img :src="props.book_params.img_url" :alt="props.book_params.title" class="card-image" />
    <h1 class="title">{{ props.book_params.title }}</h1>
    <p class="auth">{{ props.book_params.author }}</p>
    <p class="desc">{{ props.book_params.description }}</p>
  </div>
</template>

<style lang="scss" scoped>
.card {
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  background-color: #fff;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  height: fit-content;
}

img {
  width: 100%;
  height: auto;
  border-radius: 4px;
  margin-bottom: 8px;
}

.title {
  font-size: 1.2em;
  font-weight: bold;
  margin: 8px 0;
}

.auth {
  font-size: 1em;
  color: #555;
  margin-bottom: 8px;
}

.desc {
  font-size: 0.9em;
  color: #777;
}
</style>
