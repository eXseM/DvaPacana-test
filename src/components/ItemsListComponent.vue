<script setup>
import { useItemsStore } from "@/stores/ItemsStore.js";

const store = useItemsStore();
</script>

<template>
  <div class="items">
    <div class="items__list">
      <div class="items__cards" v-for="(multiple, idx) of store.multipleItems" :key="multiple.id">
        <div @click="store.selectItems(multiple, idx)" class="items__card">{{ multiple.name }}</div>
      </div>
    </div>
    <div class="items__list">
      <div class="items__cards" v-for="single of store.singleItems" :key="single.id">
        <div @click="store.selectItem(single)" class="items__card">{{ single.name }}</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.items {
  display: flex;
  flex-direction: row;
  justify-content: space-between;

  &__list {
    display: flex;
    flex-direction: row;
    border: 3px solid black;
    height: 20vh;
    min-width: 500px;
  }
  &__cards {
    width: 50px;
    height: 50px;
    border: 2px solid black;
    margin: 5px;
  }
  &__card {
    width: 100%;
    height: 100%;
    cursor: pointer;
  }
}
</style>
