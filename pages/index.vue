<template>
  <div class="container mx-auto lg:mt-0 my-24">
    <section
      class="lg:justify-between justify-center items-center text-start lg:flex block"
    >
      <div class="font-semibold mx-4 py-10">
        <p class="lg:text-8xl text-4xl">Tovuq</p>
        <div class="text-animation lg:text-8xl text-4xl" style="color: #f9e01a">
          <span class="old-text" :key="currentIndex">{{ oldText }}</span>
          <span class="new-text">{{ newText }}</span>
        </div>
        <p class="lg:my-6 lg:text-8xl text-4xl">bizdan oling</p>
        <NuxtLink
          to="/products"
          class="NuxtlinkButton z-0 top-20 hidden lg:inline-block"
          style="--clr: #f9e01a"
          ><span class="text-xl">Mahsulotlar</span><i></i
        ></NuxtLink>
      </div>
      <div class="items-center px-[95px] hidden lg:block">
        <img src="/main.png" alt="" />
      </div>
      <div class="flex lg:hidden justify-center items-center">
        <img src="/mobile/main.svg" alt="" />
      </div>
    </section>
    <section
      class="bg-no-repeat lg:min-h-[810px] lg:bg-[url('/section2.png')]"
      style="@media (max-width: 768px) {background-image: none}"
    >
      <h1
        class="text-center font-semibold lg:text-5xl text-3xl lg:pt-[2%] pt-[4%]"
      >
        Bizning afzalliklar
      </h1>
      <div class="lg:ml-[20%] mx-4 my-2 lg:mt-16 font-medium flex flex-col">
        <div class="lg:my-10 my-5">
          <h2 class="lg:text-xl text-lg">Halollik</h2>
          <p class="max-w-[250px] text-sm lg:text-lg" style="color: #7e7e7e">
            Bizda ishlab chiqarilgan mahsulotlar to‘laqonli ravishda qassoblar
            tomonidan so‘yiladi
          </p>
        </div>
        <div class="lg:inline-block hidden lg:my-10 my-5">
          <h2 class="lg:text-xl text-lg">Tozalik</h2>
          <p class="max-w-[250px] text-sm lg:text-lg" style="color: #7e7e7e">
            Har bir mahsulot alohida qadoqlanadi va upakovka qilinadi
          </p>
        </div>

        <div
          class="lg:hidden inline-block lg:my-10 my-5 lg:max-w-[250px] max-w-[200px] self-end"
        >
          <h2 class="lg:text-xl text-lg text-end">Tozalik</h2>
          <p class="text-end text-sm lg:text-lg" style="color: #7e7e7e">
            Har bir mahsulot alohida qadoqlanadi va upakovka qilinadi
          </p>
        </div>
        <div class="lg:my-10 my-5">
          <h2 class="lg:text-xl text-lg">Yetkazib berish xizmati</h2>
          <p class="max-w-[250px] text-sm lg:text-lg" style="color: #7e7e7e">
            O‘zbekiston bo‘ylab istalgan joyga yetkazib berish xizmati mavjud.
            Yetkazib berish mobaynida mahsulot sifati kafolatlanadi.
          </p>
        </div>
      </div>
    </section>
    <section class="mb-[10%] mx-2">
      <h1
        class="flex justify-center font-semibold lg:text-5xl text-3xl pt-[4%]"
      >
        Bizning mahsulotlar
      </h1>
      <div class="grid lg:grid-cols-3 gap-4 md:grid-cols-3 grid-cols-2 pt-[4%]">
        <div v-for="item in products" :key="item">
          <ProductItemsIndex :product="item" />
        </div>
      </div>
      <NuxtLink to="/products">
        <button
          class="float-right bg-yellow-300 lg:text-3xl text-sm lg:py-3 py-2 lg:px-10 px-4 rounded-3xl font-semibold flex items-center"
        >
          <div>Barchasini ko‘rish</div>
          <img src="/back.png" alt="" class="ml-4" />
        </button>
      </NuxtLink>
    </section>
    <section class="lg:block hidden">
      <h1
        class="flex text-center justify-center mx-16 font-semibold text-5xl pt-[4%]"
      >
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
    <hr class="lg:hidden bg-black mt-12 p-0.5">
    <section class="lg:my-[5%] py-[10%] lg:mx-[20%]">
      <div class="flex items-center justify-center mx-[10%] lg:mx-0">
        <div class="hidden lg:inline-block">
          <img src="/callcenterimg.png" alt="" />
        </div>
        <div class="lg:border lg:border-gray-300 lg:rounded-r-3xl lg:min-h-[480px] lg:px-5">
          <h1 class="lg:pt-10 lg:text-2xl text-xl font-semibold mb-10 text-center">
            Sizga yordam bera olamizmi ?
          </h1>
          <p class="lg:px-10 lg:max-w-[400px] text-sm">
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
import Swal from "sweetalert2";

let name = ref("");
let phone = ref("");

const handleSubmit = (e) => {
  e.preventDefault();
  if (!name.value || !phone.value) {
    return;
  } else {
    let text = `<b>Name:</b> ${name.value}\n<b>Phone</b>: ${phone.value}`;
    axios
      .get(
        `https://api.telegram.org/bot6114548691:AAFu2HvH1aswXEWFHPbxQFdkf_vkyS4ON4Q/sendMessage?chat_id=@hasghdgashdgashdght2783467238427&text=${encodeURIComponent(
          text
        )}&parse_mode=HTML`
      )
      .then((res) => {
        Swal.fire({
          position: "center",
          icon: "success",
          title: "Xabaringiz Yetkazildi",
        });
      })
      .catch((err) => {
        Swal.fire({
          position: "center",
          icon: "error",
          title: "Xatolik",
        });
      });
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
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700;800;900&display=swap");

html {
  font-family: "Poppins", sans-serif;
}
.NuxtlinkButton {
  position: relative;
  background: #000;
  color: #000;
  text-transform: uppercase;
  font-size: 1.5em;
  letter-spacing: 0.1em;
  padding: 10px 30px;
  transition: 0.5s;
}
.NuxtlinkButton:hover {
  letter-spacing: 0.25em;
  background: var(--clr);
  box-shadow: 0 0 35px var(--clr);
  color: var(--clr);
}
.NuxtlinkButton::before {
  content: "";
  position: absolute;
  inset: 2px;
  background: #fff;
}
.NuxtlinkButton span {
  position: relative;
  z-index: 1;
}
.NuxtlinkButton i {
  position: absolute;
  inset: 0;
  display: block;
}
.NuxtlinkButton i::before {
  content: "";
  position: absolute;
  width: 20px;
  height: 10px;
  left: 80%;
  top: -3.5px;
  transform: translateX(-50%);
  border: 2px solid #000;
  background-color: #fff;
  transition: 0.5s;
}
.NuxtlinkButton:hover i::before {
  width: 40px;
  left: 20%;
  border: 2px solid var(--clr);
}
.NuxtlinkButton i::after {
  content: "";
  position: absolute;
  width: 20px;
  height: 10px;
  left: 20%;
  transform: translateX(-50%);
  bottom: -3.5px;
  border: 2px solid #000;
  background-color: #fff;
  transition: 0.5s;
}
.NuxtlinkButton:hover i::after {
  width: 40px;
  left: 80%;
  border: 2px solid var(--clr);
}
.text-animation {
  position: relative;
  height: 1em;
  z-index: 0;
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
