<template>
  <div class="container mx-auto my-[3%]">
    <section class="justify-between flex">
      <div class="text-8xl font-semibold">
        <p class="my-6">Tovuq</p>
        <div class="text-animation" style="color: #f9e01a">
          <span class="old-text" :key="currentIndex">{{ oldText }}</span>
          <span class="new-text">{{ newText }}</span>
        </div>
        <p class="my-6">bizdan oling</p>
      </div>
      <div class="items-center py-[6%] px-[95px]">
        <img src="/main.png" alt="" />
      </div>
    </section>
    <section
      class="bg-no-repeat min-h-[810px] mt-[5%]"
      style="background-image: url('/section2.png')"
    >
      <h1 class="ml-[20%] font-semibold text-5xl pt-[4%]">
        Bizning afzalliklar
      </h1>
      <div class="ml-[20%] mt-16 font-medium flex flex-col">
        <div class="my-10">
          <h2 class="text-xl">Halollik</h2>
          <p class="max-w-[250px]" style="color: #7e7e7e">
            Bizda ishlab chiqarilgan mahsulotlar to‘laqonli ravishda qassoblar
            tomonidan so‘yiladi
          </p>
        </div>
        <div class="my-10">
          <h2 class="text-xl">Tozalik</h2>
          <p class="max-w-[250px]" style="color: #7e7e7e">
            Har bir mahsulot alohida qadoqlanadi va upakovka qilinadi
          </p>
        </div>
        <div class="my-10">
          <h2 class="text-xl">Yetkazib berish xizmati</h2>
          <p class="max-w-[250px]" style="color: #7e7e7e">
            O‘zbekiston bo‘ylab istalgan joyga yetkazib berish xizmati mavjud.
            Yetkazib berish mobaynida mahsulot sifati kafolatlanadi.
          </p>
        </div>
      </div>
    </section>
    <section class="mb-[10%]">
      <h1 class="flex justify-center font-semibold text-5xl pt-[4%]">
        Bizning mahsulotlar
      </h1>
      <div class="grid lg:grid-cols-3 gap-4 md:grid-cols-3 grid-cols-1 pt-[4%]">
        <div v-for="item in products" :key="item">
          <ProductItem :product="item" />
        </div>
      </div>
      <NuxtLink to="/products">
        <button
          class="float-right bg-yellow-300 text-3xl py-3 px-10 rounded-3xl font-semibold flex items-center"
        >
          <div>Barchasini ko‘rish</div>
          <img src="/back.png" alt="" class="ml-4" />
        </button>
      </NuxtLink>
    </section>
    <section>
      <h1 class="flex justify-center font-semibold text-5xl pt-[4%]">
        Bizning hamkorlar
      </h1>
      <div class="flex items-center justify-between mt-[5%]">
        <div>
          <img src="/korzinka.png" alt="" />
        </div>
        <div>
          <img src="/havas.png" alt="" />
        </div>
        <div>
          <img src="/qanotchi.png" alt="" />
        </div>
        <div>
          <img src="/magnum.png" alt="" />
        </div>
      </div>
    </section>
    <section class="my-[20%] mx-[20%]">
      <div class="flex items-center">
        <div>
          <img src="/callcenterimg.png" alt="" />
        </div>
        <div class="p-10 border border-gray-300 rounded-r-3xl">
          <h1 class="text-2xl font-semibold mb-10">
            Sizga yordam bera olamizmi ?
          </h1>
          <p class="max-w-[400px] text-sm">
            Siz istagan barcha savollaringizga bizda albatta javob bor. Agar
            yuqorida yetarlicha ma’lumot yo‘q bo‘lsa, unda telefon raqamingizni
            yozib qoldiring. Biz siz bilan albatta bog‘lanamiz
          </p>
          <form class="mt-10 flex flex-col" @submit="handleSubmit">
            <input
              type="text"
              placeholder="Ismingiz"
              class="text-sm border py-3 px-10 rounded-3xl mb-[5%]"
              v-model="name"
            />
            <input
              type="text"
              placeholder="Telefon raqamingiz"
              class="text-sm border py-3 px-10 rounded-3xl mb-[5%]"
              v-model="phone"
            />
            <button
              class="bg-yellow-300 text-lg py-3 px-10 rounded-3xl font-semibold flex items-center justify-center"
            >
              <div>Yuborish</div>
              <img src="/back.png" alt="" class="ml-4" />
            </button>
          </form>
        </div>
      </div>
    </section>
  </div>
</template>
<script setup>
import axios from "axios";
import { ref } from "vue";
import Swal from 'sweetalert2';

let name = ref("");
let phone = ref("");

const handleSubmit = (e) => {
  e.preventDefault();
  if (!name.value || !phone.value) {
    return;
  } else {
    let text = `<b>Name:</b> ${name.value}\n<b>Phone</b>: ${phone.value}`;
    axios.get(
        `https://api.telegram.org/bot6114548691:AAFu2HvH1aswXEWFHPbxQFdkf_vkyS4ON4Q/sendMessage?chat_id=@hasghdgashdgashdght2783467238427&text=${encodeURIComponent(text)}&parse_mode=HTML`
      )
      .then((res) => {
        Swal.fire({
          position: 'center',
          icon: 'success',
          title: 'Xabaringiz Yetkazildi'
        })
      })
      .catch((err) =>{
        Swal.fire({
          position: 'center',
          icon: 'error',
          title: 'Xatolik'
        })
      })
      name.value = "";
      phone.value = "";
  }
};
definePageMeta({
  pageTransition: {
    name: "rotate",
  },
});
</script>
<script>
import data from "~/items/products.json";
export default {
  data() {
    return {
      texts: ["go'shtini", "boldirini", "sonini", "oyoqchalarini", "qiymasini"],
      oldText: "",
      newText: "",
      currentIndex: 0,
      products: [],
    };
  },
  mounted() {
    this.oldText = this.texts[0];
    this.newText = this.texts[1];
    setInterval(() => {
      this.currentIndex = (this.currentIndex + 1) % this.texts.length;
      this.oldText = this.newText;
      this.newText = this.texts[this.currentIndex];
    }, 2000);
  },
  created() {
    this.products = data.slice(0, 6);
  },
};
</script>

<style>
.text-animation {
  position: relative;
  height: 1em;
}

.old-text {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  animation: slideup 2s;
}

.new-text {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  animation: slidedown 2s;
}

@keyframes slideup {
  from {
    top: 0;
    opacity: 1;
  }
  to {
    top: -1.5em;
    opacity: 0;
  }
}

@keyframes slidedown {
  from {
    bottom: -1.5em;
    opacity: 0;
  }
  to {
    bottom: 0;
    opacity: 1;
  }
}
</style>
