<template>
  <div class="relative">
    <div class="absolute bg-red-500 text-white h-5 w-5 rounded-full -right-1 -top-1 text-sm">
      {{totalQuantity}}
    </div>
    <NuxtLink to="/cart"><img src="/bag.png" alt="" /></NuxtLink>
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