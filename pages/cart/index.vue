<template>
  <div class="bg-gray-300 py-[0.3%] h-full my-24 lg:my-0">
    <div
      class="container mx-auto bg-white rounded-t-3xl my-[2%] py-8 lg:max-w-[1200px]"
    >
      <div class="flex items-center justify-between text-center lg:mx-16 mx-2 pb-[2%]">
        <NuxtLink to="/">
          <div>
            <img src="/backicon.svg" alt="" />
          </div>
        </NuxtLink>
        <h1 class="font-semibold text-3xl">Savatcha</h1>
        <div></div>
      </div>
      <div
        v-if="counterStore.count.length > 0"
        class="flex flex-col lg:mx-16 mx-2"
      >
        <div
          v-for="item in counterStore.count"
          :key="item.id"
          class="lg:my-2 my-6"
        >
          <CartItem :item="item" />
        </div>
      </div>
      <div
        v-if="counterStore.count.length > 0"
        class="flex justify-end lg:mx-16 mx-2 font-medium lg:text-2xl text-xl pt-[4%]"
      >
        <div class="flex">
          <div class="lg:mx-5 mx-2">Umumiy mahsulot</div>
          <div>{{ totalQuantity }} ta</div>
        </div>
      </div>
      <div v-else class="lg:text-3xl flex flex-col justify-center items-center text-center lg:p-[10%] p-0 text-2xl">
        <img src="/cart2.svg" alt="">
        <div class="text-gray-400 lg:py-20 py-[10%]">Hozircha mahsulot tanlanmagan</div>
      </div>
      <div
        v-if="counterStore.count.length > 0"
        class="flex justify-end lg:mx-16 mx-2 font-bold lg:text-3xl text-xl pt-[1%]"
      >
        {{ totalPrice.toLocaleString() }} so‘m
      </div>
      <div
        v-if="counterStore.count.length > 0"
        class="lg:flex block lg:justify-between lg:mx-20 mx-2 my-8 items-center lg:text-2xl text-sm text-center"
      >
        <div class="border border-gray-300 py-4 rounded-xl px-8 mb-4" style="border: 1px solid #f9e01a">
          <NuxtLink to="/products">
            <button>Sotuvni davom ettirish</button>
          </NuxtLink>
        </div>
        <div class="bg-yellow-300 py-4 rounded-xl px-8">
          <NuxtLink to="/cart/submit">
            <button>Sotuvni tasdiqlash</button>
          </NuxtLink>
        </div>
      </div>
      <div
        v-else
        class="lg:flex block lg:justify-center lg:mx-20 mx-2 my-8 items-center lg:text-2xl text-sm text-center"
      >
        <div class="border border-gray-300 py-4 rounded-xl px-8 mb-4" style="border: 1px solid #f9e01a">
          <NuxtLink to="/products">
            <button>Sotuvni davom ettirish</button>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { useCounterStore } from "~/store";

const counterStore = useCounterStore();
const totalQuantity = computed(() => {
  return counterStore.count.reduce((total, product) => {
    return total + product.quantity;
  }, 0);
});
const totalPrice = computed(() => {
  return counterStore.count.reduce((total, product) => {
    let price = product.price.replace(" so‘m", "").replace(".", "");
    return total + parseInt(price) * product.quantity;
  }, 0);
});
definePageMeta({
  pageTransition: {
    name: "rotate",
  },
});
</script>
