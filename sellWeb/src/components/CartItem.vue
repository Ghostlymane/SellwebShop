<script setup>

</script>

<template>
  <div class="cardItemInDrawer">
    <img src="/sneakers/sneakers-1.jpg" alt="Sneaker" class="ImageItem">

    <div class="TextToLeftElem">
      <p>Кроссовки Nike Air Max 279</p>

      <div class="TextCellProd">
        <b>12990 руб.</b>
        <img src="/close.svg" alt="" class="IconClose">
      </div>
    </div>
  </div>
</template>

<style scoped>
.cardItemInDrawer {
  display: flex;
  border: 1px;
  border-color: rgb(226 232 240);
  padding: 16px;
  border-radius: 12px;
  align-items: center;
  gap: 16px;
}

.TextToLeftElem {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}

.ImageItem {
  width: 64px;
  height: 64px;
}

.TextCellProd {
  display: flex;
  justify-content: space-between;
  margin-top: 8px;
}

.IconClose {
  opacity: 0.4;
  transition: 0s;
}

.IconClose:hover {
  cursor: pointer;
  opacity: 1;
}
</style>
