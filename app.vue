<template>
  <div>
    <Head>
      <Title>BAHRA</Title>
    </Head>
    <NuxtLayout />
  </div>
</template>
<style>
.page-enter-active,
.page-leave-active {
  transition: all 0.1s;
}
.page-enter-from,
.page-leave-to {
  opacity: 0;
  filter: blur(4rem);
}
.rotate-enter-active,
.rotate-leave-active {
  transition: all 0.2s;
}
.rotate-enter-from,
.rotate-leave-to {
  opacity: 0;
  transform: rotate3d(1, 1, 3, 18deg);
}
</style>
