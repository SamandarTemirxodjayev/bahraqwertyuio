<template>
  <div class="bg-gray-300 py-[0.3%] h-full my-24 lg:my-0">
    <div
      class="container mx-auto bg-white rounded-t-3xl my-[2%] py-8 lg:max-w-[1200px]"
    >
      <div class="flex items-center justify-between lg:mx-16 mx-2 pb-[2%]">
        <NuxtLink to="/cart">
          <div>
            <img src="/backicon.svg" alt="" />
          </div>
        </NuxtLink>
        <h1 class="font-semibold lg:text-5xl text-3xl">Savatcha</h1>
        <div></div>
      </div>
      <div class="flex justify-center mt-[4%] lg:mx-24">
        <form class="flex flex-col max-w-[90%]" @submit="handleSubmit">
          <input
            type="text"
            placeholder="Ismingiz"
            class="text-2xl border py-3 px-10  rounded-3xl mb-[10%]"
            :class="{ 'border-lime-700': name, 'border-red-500': !name }"
            v-model="name"
          />
          <input
            type="text"
            placeholder="Telefon raqamingiz"
            class="text-2xl border py-3 px-10 rounded-3xl mb-[80%]"
            :class="phoneClasses"
            v-model="phone"
          />
          <button
            type="submit"
            class="font-semibold bg-yellow-300 rounded-3xl px-10 py-3 text-2xl"
          >
            Jo‘natish
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
import axios from "axios";
import { useCounterStore } from "~/store";
import Swal from 'sweetalert2';

const counterStore = useCounterStore();
if (counterStore.count.length === 0) {
  navigateTo("/products");
}

let name = ref("");
let phone = ref("");

const phoneClasses = computed(() => {
  return {
    "border-lime-700": phone.value && phone.value.length >= 7,
    "border-red-500": !phone.value || phone.value.length < 7,
  };
});

const handleSubmit = (e) => {
  e.preventDefault();
  if (!name.value || !phone.value || phone.value.length < 7) {
    return;
  } else {
    let text = `<b>Name:</b> ${name.value}\n<b>Phone</b>: ${phone.value}\n<b>Order</b>:`;
    counterStore.count.forEach((item) => {
      text += `\n<b>ID</b>: ${item.id}\n<b>Name</b>: ${item.name}\n<b>Price</b>: ${item.price}\n<b>Quantity</b>: ${item.quantity}\n---------`;
    });

    axios.get(
        `https://api.telegram.org/bot1649981483:AAEZvq30no8ZIHKw3nHr2lP9-EG7gKB05iI/sendMessage?chat_id=@hasghdgashdgashdght2783467238427&text=${encodeURIComponent(text)}&parse_mode=HTML`
      )
      .then((res) => {
        Swal.fire({
          position: 'center',
          icon: 'success',
          title: 'Tez orada siz bilan operatorlar bog\'lanadi'
        })
        counterStore.resetAll();
        navigateTo("/products");
      })
      .catch((err) => console.log(err));
  }
};
</script>
