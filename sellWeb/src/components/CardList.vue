<script setup>
import { inject } from "vue";
import Card from "./Card.vue";

defineProps({
  items: Array
})
let onClickAdd = () => {
  alert('Добавить!')
}

let addToFavorite = inject('addToFavorite')
</script>

<template>
  <div class="NetItems">
    <Card
      v-for="item in items"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :imageUrl="item.imageUrl"
      :price="item.price"
      :oneClickAdd= "onClickAdd"
      :onClickFavorite="() => addToFavorite(item)"
      :isFavorite="item.isFavorite"
    />
  </div>
</template>

<style scoped>
.NetItems {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 20px;
}
</style>
