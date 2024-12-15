<script setup>
import CartItem from "./CartItem.vue";
</script>

<template>
  <div class="NetItems">
    <CartItem />
    <CartItem />
    <CartItem />
    <CartItem />
    <CartItem />
  </div>
</template>

<style scoped>
.NetItems {
  display: flex;
  flex-direction: column;
  gap: 16px;
  flex: 1 1 0%;
  justify-content: space-between;
}
</style>
