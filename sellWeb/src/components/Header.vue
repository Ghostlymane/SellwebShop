<script setup>

</script>

<template>
  <header class="header">

    <div class="LiSp">
      <img src="/logo.png" alt="Logo" class="Logo">
      <div>
        <h2 class="textThisShop">Vue Shop</h2>
        <p class="textThisUnderShop">Магазин кроссовок</p>
      </div>
    </div>

    <ul class="rightSide">
      <li class="liRightSide">
        <img src="/cart.svg" alt="Cart">
        <b>1285 руб.</b>
      </li>

      <li class="liRightSide2">
        <img src="/heart.svg" alt="Cart">
        <span>Закладки</span>
      </li>

      <li class="liRightSide3">
        <img src="/profile.svg" alt="Cart">
        <span>Профиль</span>
      </li>
    </ul>

  </header>
</template>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  border-color: rgb(226 232 240);
  padding-left: 40px;
  padding-right: 40px;
  padding-top: 32px;
  padding-bottom: 32px;
}

.Logo {
  width: 2.5rem;
}

.LiSp {
  display: flex;
  align-items: center;
  gap: 16px;
}

.textThisShop {
  font-size: 20px;
  line-height: 28px;
  font-weight: 700;
  text-transform: uppercase;
}

.textThisUnderShop {
  color: rgb(148 163 184);
}

.rightSide {
  display: flex;
  align-items: center;
  gap: 40px;
}

.liRightSide {
  display: flex;
  align-items: center;
  gap: 12px;
  color: rgb(107 114 128);
}

.liRightSide:hover {
  color: rgb(0 0 0);
  cursor: pointer;
}

.liRightSide2 {
  display: flex;
  align-items: center;
  gap: 12px;
  color: rgb(107 114 128);
}

.liRightSide2:hover {
  color: rgb(0 0 0);
  cursor: pointer;
}

.liRightSide3 {
  display: flex;
  align-items: center;
  gap: 12px;
  color: rgb(107 114 128);
}

.liRightSide3:hover {
  color: rgb(0 0 0);
  cursor: pointer;
}
</style>
