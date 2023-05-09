<template>
  <div class="container mx-auto w-full flex flex-col items-center justify-center">
    <div class="w-full">
      <img src="/logo2.png" alt="" class="mx-auto" />
    </div>
    <h1 class="font-semibold text-5xl mt-[2%]">Kompaniyamiz haqida</h1>
    <div class="flex items-center justify-center mx-auto mt-[2%]">
      <div class="flex w-[30%] font-normal text-2xl">
        <p class="leading-6">
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
      <div class="mx-[5%]">
        <img src="/aboutgroup.png" alt="" />
      </div>
    </div>
    <h1 class="font-semibold text-5xl mt-[6%]">Bizning shiorimiz</h1>
    <div class="flex justify-between my-[4%]">
      <div class="max-w-[189px] -mx-[40%]">
        <h1 class="font-medium text-4xl mb-2">Halollik</h1>
        <p class="text-lg">
          Biz bilan birga hamkorlik qiluvchi va kompaniyaga bevosita bog‘liq
          insonlar oldida halol bo‘lish juda ham muhim.
        </p>
      </div>
      <div class="max-w-[189px] -mx-[40%]">
        <h1 class="font-medium text-4xl mb-2">Tozalik</h1>
        <p class="text-lg">
          Har bir mahsulot va uni ishlab chiqarish, yetkazib berishda tozalikka
          qat’iy amal qilinadi.
        </p>
      </div>
      <div class="max-w-[189px] -mx-[40%]">
        <h1 class="font-medium text-4xl mb-2">Ishonchlilik</h1>
        <p class="text-lg">
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