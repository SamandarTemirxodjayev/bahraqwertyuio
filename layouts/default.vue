<template>
  <div>
    <div class="mx-4 my-2 flex flex-row justify-between items-center text-2xl">
      <div>
        <NuxtLink to="/"><img src="/logo.png" alt="Logo" /></NuxtLink>
      </div>
      <div>
        <ul class="flex flex-row">
          <li class="mx-4">
            <NuxtLink to="/"><span>Asosiy</span></NuxtLink>
          </li>
          <li class="mx-4">
            <NuxtLink to="/about"><span>Haqida</span></NuxtLink>
          </li>
          <li class="mx-4">
            <NuxtLink to="/products"><span>Mahsulotlar</span></NuxtLink>
          </li>
          <li class="mx-4">
            <NuxtLink to="/contact"><span>Aloqa</span></NuxtLink>
          </li>
          <li class="mx-4">
            <NuxtLink to="/cart">
              <span class="mr-2">Savatcha({{ totalQuantity }})</span>
            </NuxtLink>
          </li>
        </ul>
      </div>
      <div class="flex flex-row text-center ">
        <ul class="flex flex-row items-center">
          <li class="mx-2">
            <NuxtLink to="/"><img src="/like.png" alt="" /></NuxtLink>
          </li>
          <li class="mx-2">
            <NuxtLink to="/cart"><img src="/bag.png" alt="" /></NuxtLink>
          </li>
        </ul>
      </div>
    </div>
    <hr class="bg-gray-400" />
    <NuxtPage />
    <div class="mx-auto" style="background-color: #f9e01a">
      <div class="mx-10 mr-32 flex flex-row justify-between items-center">
        <div>
          <img src="/footerlogo.png" alt="" />
        </div>
        <div class="flex flex-col">
          <h2 class="text-2xl font-medium">Mahsulotlar</h2>
          <span class="text-xl cursor-pointer"><NuxtLink to="/">Aksiyalar</NuxtLink></span>
          <span class="text-xl cursor-pointer"><NuxtLink to="/">Kontaktla</NuxtLink>r</span>
        </div>
        <div class="flex flex-col">
          <h2 class="text-2xl font-medium">Korxona haqida</h2>
          <span class="text-xl cursor-pointer"><NuxtLink to="/">Hamkorlar</NuxtLink></span>
          <span class="text-xl cursor-pointer"><NuxtLink to="/">Aksiyalar</NuxtLink></span
          >
        </div>
        <div class="flex flex-col">
          <div class="flex-row flex">
            <NuxtLink to="/"><img src="/telegram.png" alt="" class="mx-2 cursor-pointer"/></NuxtLink>
            <NuxtLink to="/"><img src="/instagram.png" alt="" class="mx-2 cursor-pointer"/></NuxtLink>
            <NuxtLink to="/"><img src="/facebook.png" alt="" class="mx-2 cursor-pointer"/></NuxtLink>
          </div>
          <div class="mt-1 font-semibold">+998 (90) 000 00 00</div>
          <div class="font-semibold">Call center</div>
        </div>
      </div>
      <img src="/line.png" alt="" class="mx-auto py-10 object-cover" />
      <div class="text-center items-center justify-between mx-32 flex font-semibold">
        <span>© "Bahra Chickens", 2023</span>
        <span>Barcha huquqlar himoyalangan.</span>
      </div>
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
</script>
