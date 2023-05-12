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
    <section>
      <h1 class="flex justify-center font-semibold text-5xl pt-[4%]">
        Bizning hamkorlar
      </h1>
      <div class="flex items-center justify-between mt-[10%]">
        <div>
          <img src="/korzinka.png" alt="">
        </div>
        <div>
          <img src="/havas.png" alt="">
        </div>
        <div>
          <img src="/qanotchi.png" alt="">
        </div>
        <div>
          <img src="/magnum.png" alt="">
        </div>
      </div>
    </section>
  </div>
</template>
<script setup>
definePageMeta({
  pageTransition: {
    name: 'rotate'
  }
})
</script>
<script>
export default {
  data() {
    return {
      texts: ['go\'shtini', 'boldirini', 'sonini', 'oyoqchalarini', 'qiymasini'],
      oldText: '',
      newText: '',
      currentIndex: 0
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
  }
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
