<template>
  <div class="relative">
    <div class="absolute bg-red-500 text-center text-white h-7 w-7 lg:h-5 lg:w-5 rounded-full -right-1 -top-1 text-sm lg:p-0 p-1" >
      {{totalQuantity}}
    </div>
    <NuxtLink to="/cart"><img src="/bag.svg" alt="" height="60" width="60" class="lg:h-12 lg:w-12" /></NuxtLink>
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