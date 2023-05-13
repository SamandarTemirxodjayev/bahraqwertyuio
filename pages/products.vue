<template>
  <div class="my-20 lg:my-0">
    <h1 class="font-semibold text-5xl py-3 flex justify-center">Mahsulotlar</h1>
    <div class="grid lg:grid-cols-5 gap-4 lg:mx-16 mx-4 md:grid-cols-3 grid-cols-1">
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
import data from "~/items/products.json";
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
