<template>
  <div>
    <div
      class="mx-4 my-2 lg:flex flex-row justify-between items-center text-2xl hidden"
    >
      <div>
        <NuxtLink to="/"><img src="/logo.png" alt="Logo" /></NuxtLink>
      </div>
      <div>
        <ul class="flex flex-row">
          <li class="mx-4">
            <NuxtLink to="/"><span>Asosiy</span></NuxtLink>
          </li>
          <li class="mx-4">
            <NuxtLink to="/about"><span>Haqida</span></NuxtLink>
          </li>
          <li class="mx-4">
            <NuxtLink to="/products"><span>Mahsulotlar</span></NuxtLink>
          </li>
          <li class="mx-4">
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
      class="fixed bg-white w-full p-2 flex flex-row justify-between items-center text-2xl lg:hidden"
    >
      <div>
        <NuxtLink to="/">
          <img src="/logo.png" alt="Logo" />
        </NuxtLink>
      </div>
      <div class="flex flex-row text-center md:hidden">
        <button @click="hamburger">
          <div v-if="!hamburgerf">
            <svg
              viewBox="0 0 20 20"
              fill="currentColor"
              class="menu-icon w-6 h-6"
            >
              <path
                fill-rule="evenodd"
                d="M2 4h16a1 1 0 110 2H2a1 1 0 110-2zm0 6h16a1 1 0 110 2H2a1 1 0 110-2zm0 6h16a1 1 0 110 2H2a1 1 0 110-2z"
                clip-rule="evenodd"
              ></path>
            </svg>
          </div>
          <div v-else>
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
        </button>
      </div>
      <div class="flex flex-row text-center">
        <ul class="flex flex-row items-center">
          <li class="mx-2">
            <NuxtLink to="/loved">
              <img src="/like.png" alt="" />
            </NuxtLink>
          </li>
          <li class="mx-2">
            <BagItem />
          </li>
        </ul>
      </div>
    </div>
    <div v-if="hamburgerf" class="fixed bg-white w-full top-20">
      <ul class="flex flex-col" @click="hamburger">
        <li class="text-3xl my-2 text-center">
          <NuxtLink to="/">
            <span>Asosiy</span>
          </NuxtLink>
        </li>
        <li class="text-3xl my-2 text-center">
          <NuxtLink to="/about">
            <span>Haqida</span>
          </NuxtLink>
        </li>
        <li class="text-3xl my-2 text-center">
          <NuxtLink to="/products">
            <span>Mahsulotlar</span>
          </NuxtLink>
        </li>
        <li class="text-3xl my-2 text-center">
          <NuxtLink to="/contact">
            <span>Aloqa</span>
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
  </div>
</template>
<script setup>
import { ref } from "vue";

let hamburgerf = ref(false);
const hamburger = () => {
  hamburgerf.value = !hamburgerf.value;
};
</script>
