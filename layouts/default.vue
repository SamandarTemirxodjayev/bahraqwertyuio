<template>
  <div>
    <LoadSpinner v-if="showHideSpinner" />
    <div
      class="mx-4 my-2 md:hidden lg:flex flex-row justify-between items-center text-2xl hidden"
    >
      <div>
        <NuxtLink to="/"
          ><img src="/logo.svg" alt="Logo" class="rounded-3xl h-[74px] w-[148px]"
        /></NuxtLink>
      </div>
      <div>
        <ul class="flex flex-row">
          <li class="mx-8">
            <NuxtLink to="/"><span>Asosiy</span></NuxtLink>
          </li>
          <li class="mx-8">
            <NuxtLink to="/about"><span>Haqida</span></NuxtLink>
          </li>
          <li class="mx-8">
            <NuxtLink to="/products"><span>Mahsulotlar</span></NuxtLink>
          </li>
          <li class="mx-8">
            <NuxtLink to="/contact"><span>Aloqa</span></NuxtLink>
          </li>
        </ul>
      </div>
      <div class="flex flex-row text-center">
        <ul class="flex flex-row items-center">
          <li class="mx-2">
            <NuxtLink to="/loved"><img src="/like.png" alt="" /></NuxtLink>
          </li>
          <li class="mx-2">
            <BagItem />
          </li>
        </ul>
      </div>
    </div>
    <div
      class="fixed bg-white w-full px-5 flex flex-row justify-between items-center text-2xl lg:hidden"
      style="background: #f9e01a"
    >
      <div class="flex flex-row text-center lg:hidden">
        <button @click="hamburger">
          <div v-if="!hamburgerf">
            <svg
              viewBox="0 0 20 20"
              fill="currentColor"
              class="menu-icon"
              width="30"
              height="30"
            >
              <path
                fill-rule="evenodd"
                d="M2 4h16a1 1 0 110 2H2a1 1 0 110-2zm0 6h16a1 1 0 110 2H2a1 1 0 110-2zm0 6h16a1 1 0 110 2H2a1 1 0 110-2z"
                clip-rule="evenodd"
              ></path>
            </svg>
          </div>
        </button>
      </div>
      <div>
        <NuxtLink to="/">
          <img src="/logo.svg" alt="Logo" />
        </NuxtLink>
      </div>
      <div class="flex flex-row">
        <NuxtLink to="/loved">
          <img src="/like.png" alt="" />
        </NuxtLink>
      </div>
    </div>
    <div v-if="hamburgerf" class="fixed z-10 side-bar">
      <div class="close-btn" @click="hamburger">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          x="0px"
          y="0px"
          width="30"
          height="30"
          viewBox="0 0 30 30"
        >
          <path
            d="M 7 4 C 6.744125 4 6.4879687 4.0974687 6.2929688 4.2929688 L 4.2929688 6.2929688 C 3.9019687 6.6839688 3.9019687 7.3170313 4.2929688 7.7070312 L 11.585938 15 L 4.2929688 22.292969 C 3.9019687 22.683969 3.9019687 23.317031 4.2929688 23.707031 L 6.2929688 25.707031 C 6.6839688 26.098031 7.3170313 26.098031 7.7070312 25.707031 L 15 18.414062 L 22.292969 25.707031 C 22.682969 26.098031 23.317031 26.098031 23.707031 25.707031 L 25.707031 23.707031 C 26.098031 23.316031 26.098031 22.682969 25.707031 22.292969 L 18.414062 15 L 25.707031 7.7070312 C 26.098031 7.3170312 26.098031 6.6829688 25.707031 6.2929688 L 23.707031 4.2929688 C 23.316031 3.9019687 22.682969 3.9019687 22.292969 4.2929688 L 15 11.585938 L 7.7070312 4.2929688 C 7.5115312 4.0974687 7.255875 4 7 4 z"
          ></path>
        </svg>
      </div>
      <ul class="flex flex-col text-xl" @click="hamburger">
        <li>
          <NuxtLink to="/" class="NuxtLinkButton hover:rounded-2xl flex">
            <div class="flex items-center">
              <img src="/sidebar/index.svg" alt="" class="mr-5">
              <span>Asosiy</span>
            </div>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink to="/about" class="NuxtLinkButton hover:rounded-2xl">
            <div class="flex items-center">
              <img src="/sidebar/about.svg" alt="" class="mr-5">
              <span>Haqida</span>
            </div>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink to="/products" class="NuxtLinkButton hover:rounded-2xl">
            <div class="flex items-center">
              <img src="/sidebar/products.svg" alt="" class="mr-5">
              <span>Mahsulotlar</span>
            </div>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink to="/contact" class="NuxtLinkButton hover:rounded-2xl">
            <div class="flex items-center">
              <img src="/sidebar/contacts.svg" alt="" class="mr-5">
              <span>Aloqa</span>
            </div>
          </NuxtLink>
        </li>
        <li>
          <NuxtLink to="/cart" class="NuxtLinkButton hover:rounded-2xl">
            <div class="flex items-center">
              <img src="/sidebar/cart.svg" alt="" class="mr-5">
              <span>Savatcha</span>
            </div>
          </NuxtLink>
        </li>
      </ul>
    </div>
    <hr class="bg-gray-400" />
    <NuxtPage />
    <div class="mx-auto hidden lg:block" style="background-color: #f9e01a">
      <div class="mx-10 mr-32 flex flex-row justify-between items-center">
        <div>
          <img src="/footerlogo.png" alt="" />
        </div>
        <div class="flex flex-col">
          <h2 class="text-2xl font-medium">Mahsulotlar</h2>
          <span class="text-xl cursor-pointer"
            ><NuxtLink to="/">Aksiyalar</NuxtLink></span
          >
          <span class="text-xl cursor-pointer"
            ><NuxtLink to="/">Kontaktla</NuxtLink>r</span
          >
        </div>
        <div class="flex flex-col">
          <h2 class="text-2xl font-medium">Korxona haqida</h2>
          <span class="text-xl cursor-pointer"
            ><NuxtLink to="/">Hamkorlar</NuxtLink></span
          >
          <span class="text-xl cursor-pointer"
            ><NuxtLink to="/">Aksiyalar</NuxtLink></span
          >
        </div>
        <div class="flex flex-col">
          <div class="flex-row flex">
            <NuxtLink to="/"
              ><img src="/telegram.png" alt="" class="mx-2 cursor-pointer"
            /></NuxtLink>
            <NuxtLink to="/"
              ><img src="/instagram.png" alt="" class="mx-2 cursor-pointer"
            /></NuxtLink>
            <NuxtLink to="/"
              ><img src="/facebook.png" alt="" class="mx-2 cursor-pointer"
            /></NuxtLink>
          </div>
          <div class="mt-1 font-semibold">+998 (90) 000 00 00</div>
          <div class="font-semibold">Call center</div>
        </div>
      </div>
      <img src="/line.png" alt="" class="mx-auto py-10 object-cover" />
      <div
        class="text-center items-center justify-between mx-32 flex font-semibold"
      >
        <span>© "Bahra Chickens", 2023</span>
        <span>Barcha huquqlar himoyalangan.</span>
      </div>
    </div>
    <div class="lg:hidden">
      <div class="fixed bottom-5 right-5">
        <BagItem />
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref } from "vue";

let hamburgerf = ref(false);
const hamburger = () => {
  hamburgerf.value = !hamburgerf.value;
};
</script>
<style>
.side-bar {
  background: rgba(255, 255, 255);
  backdrop-filter: blur(15px);
  width: 290px;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  overflow-y: auto;
}
.side-bar ul {
  width: 100%;
  margin-top: 80px;
}
.side-bar ul li {
  position: relative;
  cursor: pointer;
}
.side-bar ul li .NuxtLinkButton {
  display: block;
  padding: 3px 15px;
  line-height: 60px;
}
.side-bar ul li .NuxtLinkButton:hover {
  background: #f9e01a;
  transition: 0.3s ease;
}
.close-btn{
  position: absolute;
  right: 0;
  margin: 25px;
  cursor: pointer;
}
</style>
<script>
export default {
  beforeCreate() {
    this.showHideSpinner = true;
  },
  mounted() {
    this.showHideSpinner = false;
  },
  data() {
    return {
      showHideSpinner: true
    };
  }
};
</script>