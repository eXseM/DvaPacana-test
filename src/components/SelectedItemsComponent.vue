<script setup>
import { useItemsStore } from "@/stores/ItemsStore.js";

const store = useItemsStore();
</script>

<template>
  <div class="items">
    <div class="items__list">
      <div class="items__cards">
        <div class="items__card" v-for="multiple of store.selectedMultiple" :key="multiple.id">
          <span>{{ multiple.name }}</span>
        </div>
      </div>
      <div class="items__selected">
        <p>
          <b>Selected: {{ store.selectedMultipleCount }} / 6</b>
        </p>
      </div>
    </div>
    <div class="items__list">
      <div class="items__cards">
        <div class="items__card" v-show="store.selectedSingle?.name">
          {{ store.selectedSingle?.name }}
        </div>
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
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    border: 3px solid black;
    margin-bottom: 5px;
    height: 200px;
    width: 260px;
  }
  &__cards {
    width: 100%;
    height: 150px;
    margin: 10px;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
  }
  &__card {
    width: 50px;
    height: 50px;
    border: 2px solid black;
    margin: 5px;
    align-content: center;
  }
}
</style>
