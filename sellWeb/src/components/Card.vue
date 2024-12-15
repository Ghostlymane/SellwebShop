<script setup>
import {inject} from "vue";

defineProps({
    id: Number,
    title: String,
    imageUrl: String,
    price: Number,
    isFavorite: Boolean,
    isAdded: Boolean,
    oneClickFavorite: Function,
    onClickAdd: Function
  })

</script>

<template>
  <div class="Card">

    <img :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
         alt="Like 1"
         class="LikeIcon"
         @click ="oneClickFavorite"
    >

    <img :src="imageUrl" alt="Sneaker">
    <p class="textFromNameItem">{{ title }}</p>

    <div class="CardSellElement">
      <div class="textUnderCard">
        <span class="textInSell">Цена</span>
        <b>{{ price }} руб.</b>
      </div>

      <img @click="oneClickAdd" :src="!isAdded ? '/plus.svg' : '/checked.svg'" alt="Plus">
    </div>
  </div>
</template>

<style scoped>

.CardSellElement {
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
}

.Card {
  position: relative;
  flex-direction: column;
  border-color: rgb(241 245 249);
  background-color: white;
  border-radius: 24px;
  padding: 38px;
  cursor: pointer;
  transition-property: color, background-color, border-color, text-decoration-color, fill, stroke, opacity, box-shadow, transform, filter, backdrop-filter;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}

.Card:hover {
  transform: translateY(-0.5rem);
}

.Card:hover {
  box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);
}

.textUnderCard {
  display: flex;
  flex-direction: column;
}

.textInSell {
  color: rgb(148 163 184);
}

.LikeIcon {
  position: absolute;
  top: 32px;
  left: 32px;
}

.textFromNameItem {
  margin-top: 8px;
}
</style>
