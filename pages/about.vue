<template>
  <div class="container mx-auto w-full flex flex-col items-center justify-center mt-20 lg:my-0">
    <div class="w-full lg:inline-block hidden">
      <img src="/logo2.svg" alt="" class="mx-auto" />
    </div>
    <h1 class="font-semibold lg:text-5xl text-2xl my-[5%] lg:my-[2%] text-center">Kompaniyamiz haqida</h1>
    <div class="flex flex-col lg:flex-row items-center justify-center mx-auto lg:mt-[2%]">
      <div class="flex lg:w-[30%] lg:font-normal font-semibold lg:text-2xl text-lg lg:mx-0 mx-[2%]">
        <p class="leading-8">
          "Bahra Chickens" bu barra tovuq go'shtlari va yarim tayyor
          mahsulotlarini ishlab chiqaruvchi kompaniyadir. Ushbu kompaniya
          2018-yil tashkil topgan. “Bahra Chickens” korxonasi sizning savdo
          rastangizni halol va ishonchli xizmat bilan to‘ldiradi. Bugungi kunga
          kelib kompaniyada 150 ga yaqin xodim faoliya olib boradi. Ular tijorat
          departament, marketing, operatsiyalar bo‘limlarida ishlaydi. <br />
          <br />Komponiyamizda ishlab chiqarilayotgan barcha mahsulotlar halol
          sertifikatiga ega bo'lib, pokizalik va halollik kompaniyaning doimiy
          nazoratidadir.
        </p>
      </div>
      <div class="lg:mx-[5%] mx-[2%] lg:my-0 my-[5%]">
        <img src="/aboutgroup.png" alt="" />
      </div>
    </div>
    <h1 class="font-semibold lg:text-5xl lg:mt-[6%] text-2xl">Bizning shiorimiz</h1>
    <div class="lg:flex justify-between lg:my-[4%]">
      <div class="lg:max-w-[189px] lg:-mx-[40%] lg:my-0 my-10 mx-[2%]">
        <h1 class="font-medium lg:text-4xl text-xl mb-2">Halollik</h1>
        <p class="lg:text-lg text-sm leading-5 lg:leading-8">
          Biz bilan birga hamkorlik qiluvchi va kompaniyaga bevosita bog‘liq
          insonlar oldida halol bo‘lish juda ham muhim.
        </p>
      </div>
      <div class="lg:max-w-[189px] lg:-mx-[40%] lg:my-0 my-10 mx-[2%]">
        <h1 class="font-medium lg:text-4xl text-xl mb-2">Tozalik</h1>
        <p class="lg:text-lg text-sm leading-5 lg:leading-8">
          Har bir mahsulot va uni ishlab chiqarish, yetkazib berishda tozalikka
          qat’iy amal qilinadi.
        </p>
      </div>
      <div class="lg:max-w-[189px] lg:-mx-[40%] lg:my-0 my-10 mx-[2%]">
        <h1 class="font-medium lg:text-4xl text-xl mb-2">Ishonchlilik</h1>
        <p class="lg:text-lg text-sm leading-5 lg:leading-8">
          Bizga ishonishingiz uchun yuqori sifatda va hamyonbop narxda mahsulot
          yetkazib berishga harakat qilamiz.
        </p>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
definePageMeta({
  pageTransition: {
    name: 'rotate'
  }
})
</script>