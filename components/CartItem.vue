<template>
  <div class="flex justify-between">
    <div class="flex">
      <div>
        <img
          :src="item.photo"
          alt=""
          class="border border-gray-300 shadow-xl rounded-2xl h-[180px] w-[260px]"
        />
      </div>
      <div class="flex justify-between">
        <div class="text-3xl px-6">
          <div class="text-semibold">
            {{ item.name }}
          </div>
          <div class="font-bold pt-6">
            {{ item.price }}
          </div>
        </div>
      </div>
    </div>
    <div class="pt-3 text-2xl">
      <div class="border border-gray-300 rounded-3xl p-2 flex items-center">
        <div class="mx-4 cursor-pointer p-2" @click="counterStore.deleteProduct(item)">
          -
        </div>
        <div class="text-semibold cursor-not-allowed">
          {{ item.quantity }}
        </div>
        <div class="mx-4 cursor-pointer p-2" @click="counterStore.add(item)">
          +
        </div>
      </div>
      <div class="float-right pt-2 pr-2 cursor-pointer" @click="counterStore.reset(item)">
        <img src="/trash.png" alt="" class="h-9 w-8">
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
};
</script>
<script setup>
import { useCounterStore } from "~/store";

const counterStore = useCounterStore();
</script>
