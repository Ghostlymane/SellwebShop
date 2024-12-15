<script setup>

</script>

<template>
  <div class="arrowNext">
    <svg
      class="btnArrowNext"
      width="16"
      height="14"
      viewBox="0 0 16 14"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path d="M1 7H14.7143"
            stroke="black"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
      />
      <path d="M8.71436 1L14.7144 7L8.71436 13"
            stroke="black"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
      />
    </svg>
    <h2 class="textInDrawer">Корзина</h2>
  </div>
</template>

<style scoped>
.textInDrawer {
  font-size: 24px;
  line-height: 32px;
  font-weight: bold;
}

.arrowNext {
  display: flex;
  align-items: center;
  gap: 32px;
  margin-bottom: 20px;
}

.btnArrowNext {
  opacity: 0.3;
  cursor: pointer;
  transform: rotate(180deg);
  transition: 0.1s;
}

.btnArrowNext:hover {
  opacity: 1;
}

.btnArrowNext:hover {
  -transform: translateX(0.25rem);
}
</style>
