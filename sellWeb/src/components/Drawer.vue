<script setup>
  import DrawerHeadWiew from "./DrawerHeadWiew.vue";
  import CardItemList from "@/components/CardItemList.vue";
</script>

<template>
    <div class="blockIsDrawer"></div>
    <div class="blockDrawer">
      <DrawerHeadWiew />

      <CardItemList />

      <div class="allTextDrawer">
        <div class="TextUnderDrawer">
          <span>Итого:</span>
          <div class="separator"></div>
          <b>12990 ₽</b>
        </div>

        <div class="TextUnderDrawer">
          <span>Налог 5%:</span>
          <div class="separator"></div>
          <b>900 ₽</b>
        </div>

        <button class="btnOffer" disabled="">Оформить заказ</button>
      </div>
    </div>

</template>

<style scoped>
.blockIsDrawer {
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background-color: black;
  z-index: 10;
  opacity: 0.7;
}

.blockDrawer {
  position: fixed;
  right: 0;
  top: 0;
  z-index: 20;
  background-color: white;
  width: 384px;
  height: 100%;
  padding: 32px;
}

.TextUnderDrawer {
  display: flex;
  gap: 8px;
}

.separator {
  flex: 1 1 0%;
  border-bottom: 0px;
  border-style: dashed;
}

.allTextDrawer {
  display: flex;
  flex-direction: column;
  gap: 16px;
  margin-bottom: 24px;
  margin-top: 28px;
  margin-bottom: 28px;
}

.btnOffer {
  background-color: rgb(132, 204, 22);
  width: 100%;
  border-radius: 12px;
  padding-top: 12px;
  padding-bottom: 12px;
  color: white;
  margin-top: 16px;
}

.btnOffer:hover {
background-color: rgb(101, 163, 13);
  transition: 0s;
  cursor: pointer;
}

.btnOffer:active {
  background-color: rgb(77, 124, 15);
  transition: 0s;
}

.btnOffer:disabled {
  background-color: rgb(203, 213, 225);
}
</style>
