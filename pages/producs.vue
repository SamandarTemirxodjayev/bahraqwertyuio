<template>
  <div class="mx-auto">
    <h1 class="font-semibold text-5xl py-3 flex justify-center">Mahsulotlar</h1>
    <div class="grid lg:grid-cols-5 gap-4 mx-16 md:grid-cols-3 grid-cols-1">
      <div v-for="item in 100" :key="item">
        <ProductItem />
      </div>
    </div>
  </div>
</template>
