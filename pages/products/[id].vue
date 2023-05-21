<template>
  <div class="my-20 lg:my-0">
    <h1 class="font-semibold lg:text-5xl text-3xl py-3 flex justify-center">{{Name}}</h1>
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
import data from "~/items/products.json";
import data2 from "~/items/products2.json";
import data3 from "~/items/products3.json";
export default {
  data() {
    return {
      products: [],
      Name: ''
    };
  },
  created() {
    if(this.$route.params.id == "1"){
      this.products = data;
      this.Name = "Muzlagan"
    }
    if(this.$route.params.id == "2"){
      this.products = data2;
      this.Name = "Yarim Tayyor"
    }
    if(this.$route.params.id == "3"){
      this.products = data3;
      this.Name = "Tayyor"
    }
  },
};
</script>
