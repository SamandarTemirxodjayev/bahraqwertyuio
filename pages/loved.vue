<template>
  <div class="mx-auto">
    <h1 class="font-semibold text-5xl py-3 flex justify-center">Mahsulotlar</h1>
    <div class="grid lg:grid-cols-5 gap-4 mx-16 md:grid-cols-3 grid-cols-1">
      <div v-for="item in products" :key="item">
        <ProductItem :product="item" />
      </div>
    </div>
  </div>
</template>
<script setup>
definePageMeta({
  pageTransition: {
    name: "rotate",
  },
});
</script>
<script>
import data from "~/items/loved.json";
export default {
  data() {
    return {
      products: [],
    };
  },
  created() {
    this.products = data;
  },
};
</script>