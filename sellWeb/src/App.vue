<script setup>
import {onMounted, reactive, ref, provide, watch} from "vue";
import axios from "axios";

import Header from "@/components/Header.vue";
import CardList from "@/components/CardList.vue";
import Drawer from "@/components/Drawer.vue";
let items = ref([])

let filters = reactive({
  sortBy: 'title',
  searchQuery: ''
})

let onChangeSelect = (event) => {
  filters.sortBy = event.target.value
}

let onChangeSearchInput = (event) => {
  filters.searchQuery = event.target.value
}

let fetchFavorites = async () => {
  try {

    let { data: favorites } = await axios.get(`https://e2a8a0be2cd31390.mokky.dev/favorites`)

    items.value = items.value.map((item) => {
      let favorite = favorites.find(favorite => favorite.parentId === item.id)

      if (!favorite) {
        return item
      }

      return {
        ...item,
        isFavorite: false,
        favoriteId: favorite.id,
      }
    })
    console.log(items.value)
  } catch (err) {
    console.log(err)
  }
}

let addToFavorite = async (item) => {
  item.isFavorite = !item.isFavorite

  console.log(item)
}

let fetchItems = async () => {
  try {
    let params = {
      sortBy: filters.sortBy,
    }

    if (filters.searchQuery) {
      params.title = `*${filters.searchQuery}*`
    }

    let { data } = await axios.get(
      `https://e2a8a0be2cd31390.mokky.dev/items`, {
        params
      })

    items.value = data.map((obj) => ({
      ...obj,
      isFavorite: false,
      isAdded: false
    }))
  } catch (err) {
    console.log(err)
  }
}

onMounted(async () => {
  await fetchItems();
  await fetchFavorites();
})
watch(filters, fetchItems)

provide('addToFavorite', addToFavorite)
</script>

<template>
<!--  <drawer/>-->
<div class="wrapper">

  <Header>
  </Header>

  <div class="allItem">
    <div class="allInfoTextB">
      <h2 class="textUnderHeader">Все кроссовки</h2>

      <div class="SearchAndSelect">
        <select @change="onChangeSelect" class="selectRend">
          <option value="name"> По названию</option>
          <option value="price">По цене(Дешёвые)</option>
          <option value="-price">По цене(Дорогие)</option>
        </select>
        <div class="BlockInputAndText">

          <img src="/search.svg" class="SearchIcon">
          <input
            @input="onChangeSearchInput"
            type="text"
            placeholder="Поиск..."
            class="inputSearchMag"
          >
      </div>

      </div>
    </div>

  <div class="CardListOpt">
    <CardList :items="items" @addToFavorite="addToFavorite"/>
  </div>
  </div>
</div>
</template>

<style scoped>

.wrapper {
  background: white;
  width: 80%;
  margin: auto;
  border-radius: 0.75rem;
  box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);
  margin-top: 3.5rem;
}

.textUnderHeader {
  font-size: 30px;
  line-height: 36px;
  font-weight: bold;
  margin-bottom: 32px;
}

.allItem {
  padding: 40px;
}

.allInfoTextB {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.inputSearchMag {
  border: none;
  border-color: rgb(229 231 235);
  border-radius: 6px;
  padding-top: 2px;
  padding-bottom: 2px;
  padding-left: 44px;
  padding-right: 16px;
}

.inputSearchMag:focus {
  border-color: rgb(156 163 175);
}

.SearchIcon {
  position: absolute;
  left: 5px;
  top: 5px;
}

.BlockInputAndText {
  position: relative;
}

.selectRend {
  padding-top: 2px;
  padding-bottom: 2px;
  padding-left: 12px;
  padding-right: 12px;
  border: 0;
  border-radius: 6px;
  outline: none;
}

.SearchAndSelect {
  display: flex;
  gap: 16px;
}

.CardListOpt {
  margin-top: 40px;
}
</style>
