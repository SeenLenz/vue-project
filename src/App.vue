<script setup lang="ts">
import TableView from './views/TableView.vue'
import CardView from './views/CardView.vue'
import { ref } from 'vue'
import booklist from './assets/bookdata'

const currentTab: any = ref('CardView')
const tabs = {
  TableView,
  CardView,
}
</script>

<template>
  <header>
    <button
      v-for="(_, tab) in tabs"
      :key="tab"
      :class="['tab-button', { active: currentTab === tab }]"
      @click="currentTab = tab"
    >
      {{ tab }}
    </button>
  </header>
  <main>
    <component :is="tabs[currentTab]" class="tab" :book="booklist"></component>
  </main>
</template>

<style lang="scss" scoped>
header {
  width: 100%;
  height: 50px;
  border-radius: 8px;
  background-color: grey;
  padding: 4px;

  button {
    padding: 2px 8px 2px 8px;
    margin: 0px 4px 0px 0px;
    border-radius: 8px;
    border: none;
    height: 100%;
  }

  .active {
    background-color: rgb(179, 179, 179);
    transition: all 0.2s;
  }
}

main {
  width: 100%;
  height: 100%;
  border-radius: 8px;
  background-color: darkgray;
}
</style>
