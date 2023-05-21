<template>
  <div class="mx-auto my-20 lg:my-0">
    <h1 class="font-semibold lg:text-5xl text-3xl py-3 flex justify-center">Saralanganlar</h1>
    <div class="grid lg:grid-cols-5 gap-4 lg:mx-16 mx-4 md:grid-cols-3 grid-cols-2">
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