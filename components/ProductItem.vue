<template>
  <div class="p-4 my-4 bg-white rounded-lg shadow-md overflow-hidden flex flex-col">
    <img :src="product.photo" alt="Product image" class="mx-auto block min-h-[130px]" />
    <div class="p-4">
      <h2 class="text-lg font-light my-2">{{ product.name }}</h2>
      <p class="text-gray-700 font-bold text-xl">{{ product.price }}</p>
    </div>
    <button
      @click="add(product)"
      class="bg-yellow-300 font-bold p-3 rounded-2xl w-full my-2 flex items-center justify-center"
    >
      <div>Savatcha</div>
      <img src="/cart.png" alt="" class="ml-2" />
    </button>
  </div>
</template>

<script setup>
import { useCounterStore } from '~/store'

const counterStore = useCounterStore()

const add = (product) => {
  counterStore.add(product)
}
</script>

<script>
export default {
  props: {
    product: {
      type: Object,
      required: true,
    },
  },
};
</script>
