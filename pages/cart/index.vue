<template>
  <div class="bg-gray-300 py-[0.3%] h-full">
    <div v-if="counterStore.count.length > 0" class="container mx-auto bg-white rounded-t-3xl my-[2%] py-8 max-w-[1200px]">
      <div class="flex items-center justify-between mx-16 pb-[2%]">
        <NuxtLink to="/">
          <div class="flex float-left">
            <img src="/backicon.png" alt="" />
          </div>
        </NuxtLink>
        <div class="">
          <h1 class="font-semibold text-5xl">Savatcha</h1>
        </div>
        <div></div>
      </div>
      <div class="flex flex-col mx-16">
        <div v-for="item in counterStore.count" :key="item.id" class="py-2">
          <CartItem :item="item" />
        </div>
      </div>
      <div class="flex justify-end mx-16 font-medium text-2xl pt-[4%]">
        <div class="flex">
          <div class="mx-5">
            Umumiy mahsulot
          </div>
          <div>
            {{totalQuantity}} ta
          </div>
        </div>
      </div>
      <div class="flex justify-end mx-16 font-bold text-3xl pt-[1%]">
        {{totalPrice.toLocaleString()}} so‘m
      </div>
      <div class="flex justify-between mx-20 my-8 items-center text-2xl">
        <div class="border border-gray-300 py-4 rounded-xl px-8">
          <NuxtLink to="/products">
            <button>Sotuvni davom ettirish</button>
          </NuxtLink>
        </div>
        <div class="bg-yellow-300 py-4 rounded-xl px-8">
          <button>Sotuvni tasdiqlash</button>
        </div>
      </div>
    </div>
    <div v-else class="container mx-auto bg-white rounded-t-3xl my-[2%] py-8 max-w-[1200px]">
      <h1 class="text-5xl font-semibold text-center">Mahsulot Mavjud Emas</h1>
    </div>
  </div>
</template>
<script setup>
import { useCounterStore } from "~/store";

const counterStore = useCounterStore();
const totalQuantity = computed(() => {
  return counterStore.count.reduce((total, product) => {
    return total + product.quantity
  }, 0)
})
const totalPrice = computed(() => {
  return counterStore.count.reduce((total, product) => {
    let price = product.price.replace(" so‘m", "").replace(".", "")
    return total + parseInt(price) * product.quantity
  }, 0)
})
definePageMeta({
  pageTransition: {
    name: "rotate",
  },
});
</script>
