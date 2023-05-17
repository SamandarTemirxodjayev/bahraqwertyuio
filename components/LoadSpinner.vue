<template>
  <div class="splash-screen">
    <div class="spinner-wrapper">
      <div>
        <div
          style="border-top-color: transparent"
          class="w-20 h-20 border-4 border-black border-dashed rounded-full animate-spin"
        ></div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.splash-screen {
  background: #f9e01a;
  width: 100vw;
  height: 100vh;
  position: fixed;
  z-index: 50;
}

.spinner-wrapper {
  position: absolute;
  left: 50%;
  top: 50%;

  transform: translate(-50%, -50%);
}

@-webkit-keyframes sk-scaleout {
  0% {
    -webkit-transform: scale(0);
  }
  100% {
    -webkit-transform: scale(1);
    opacity: 0;
  }
}

@keyframes sk-scaleout {
  0% {
    -webkit-transform: scale(0);
    transform: scale(0);
  }
  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
    opacity: 0;
  }
}
</style>
