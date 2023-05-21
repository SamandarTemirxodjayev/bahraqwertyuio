<template>
  <div class="my-20 lg:my-0 text-3xl">
    <h1 class="font-semibold lg:text-5xl py-3 flex justify-center">Mahsulotlar</h1>
    <div class="flex flex-col justify-center text-center">
      <NuxtLink
        to="/products/1"
        class="lg:my-10 my-5 border border-gray-200 rounded-2xl lg:mx-[30%] mx-[10%] lg:py-[2%] py-[10%] shadow-xl hoverFAE01A"
      >
        <button>Muzlagan</button>
      </NuxtLink>
      <NuxtLink
        to="/products/2"
        class="lg:my-10 my-5 border border-gray-200 rounded-2xl lg:mx-[30%] mx-[10%] lg:py-[2%] py-[10%] shadow-xl hoverFAE01A"
      >
        <button>Yarim tayyor</button>
      </NuxtLink>
      <NuxtLink
        to="/products/3"
        class="lg:my-10 my-5 border border-gray-200 rounded-2xl lg:mx-[30%] mx-[10%] lg:py-[2%] py-[10%] shadow-xl hoverFAE01A"
      >
        <button>Tayyor</button>
      </NuxtLink>
    </div>
  </div>
</template>
<style scoped>
  .hoverFAE01A:hover{
    background-color: #FAE01A;
    transition: all 0.5s;
  }
</style>
<script setup>
definePageMeta({
  pageTransition: {
    name: "rotate",
  },
});
</script>