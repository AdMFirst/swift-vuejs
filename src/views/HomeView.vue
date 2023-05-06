<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="background-image"></div>
  <div class="container h-100 absolute-ps z-0">
    <div class="d-flex align-items-center justify-content-center h-100">
      <div class="d-flex flex-column align-items-stretch">
        <h1 class="text align-self-center display-3 text-light m-0">Swift E-Learning</h1>
        <h3 class="text align-self-center text-light">Versi Vue App</h3>
        <p class="text align-self-center lead text-light">
          mulai mengajar sekarang!
        </p>
        <div class="d-flex justify-content-evenly p-2">
          <RouterLink to="/register">
            <button class="btn btn-light px-5" type="button">Daftar</button>
          </RouterLink>
          <RouterLink to="/login">
            <button type="button" class="btn btn-primary px-5">Masuk</button>
          </RouterLink>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.absolute-ps {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
}
.background-image{
  height: 90%;
  position: relative;

  background-image: url(../assets/background_1.png);
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;


  -webkit-filter: blur(1px) brightness(0.3);
  -moz-filter: blur(1px) brightness(0.3);
  -ms-filter: blur(1px) brightness(0.3);
  -o-filter: blur(1px) brightness(0.3);
  filter: blur(1px) brightness(0.3);

  z-index: -3;
}

</style>