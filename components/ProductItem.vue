<template>
  <div
    class="lg:p-4 p-2 lg:my-4 my-0 bg-white rounded-lg shadow-2xl overflow-hidden flex flex-col"
  >
    <img
      :src="product.photo"
      alt="Product image"
      class="mx-auto block min-h-[130px]"
    />
    <div class="lg:p-4 p-1">
      <h2 class="lg:text-lg text-sm font-light lg:my-2">
        {{
          product.name.length > 20
            ? product.name.substring(0, 20) + "..."
            : product.name
        }}
      </h2>
      <p class="text-gray-700 font-bold lg:text-xl text-sm">
        {{ product.price }}
      </p>
    </div>
    <div @click="handle">
      <button
        v-if="!handleclick"
        @click="add(product)"
        class="bg-yellow-300 lg:font-bold font-semibold lg:p-3 p-1.5 rounded-2xl w-full lg:my-2 flex items-center justify-center"
      >
        <div>Savatcha</div>
        <img src="/mobile/cart.svg" alt="" class="ml-2" />
      </button>
      <button
        v-else
        class="border border-green-500 font-semibold lg:p-3 p-1.5 rounded-2xl w-full lg:my-2 flex items-center justify-center"
      >
        <div>Qo'shildi</div>
      </button>
    </div>
  </div>
</template>

<script setup>
import { useCounterStore } from "~/store";
import { ref } from "vue";

const counterStore = useCounterStore();

const handleclick = ref(false);
const handle = () => {
  handleclick.value = true;
};

const add = (product) => {
  counterStore.add(product);
};
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
