<template>
  <div class="flex justify-between">
    <div class="flex">
      <div>
        <img
          :src="item.photo"
          alt=""
          class="border border-gray-300 shadow-xl rounded-2xl lg:h-[180px] lg:w-[260px]"
        />
      </div>
      <div class="flex justify-between">
        <div class="lg:text-3xl text-xl lg:px-6 px-3">
          <div class="text-semibold">
            {{ item.name }}
          </div>
          <div class="font-bold pt-6">
            {{ item.price }}
          </div>
        </div>
      </div>
    </div>
    <div class="pt-3 lg:text-2xl">
      <div class="border border-gray-300 rounded-3xl lg:p-2 flex items-center">
        <div class="mx-4 cursor-pointer lg:p-2" @click="counterStore.deleteProduct(item)">
          -
        </div>
        <div class="text-semibold cursor-not-allowed">
          {{ item.quantity }}
        </div>
        <div class="mx-4 cursor-pointer lg:p-2" @click="counterStore.add(item)">
          +
        </div>
      </div>
      <div class="float-right pt-2 pr-2 cursor-pointer" @click="counterStore.reset(item)">
        <img src="/trash.png" alt="" class="lg:h-9 lg:w-8 h-6 w-5">
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
