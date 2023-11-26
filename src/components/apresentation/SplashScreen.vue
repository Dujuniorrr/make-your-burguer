<template>
  <div :class="{ loader: true, fadeout: !isloading }"  class="d-flex align-items-center" >
        <!-- <LoadSpinnerVue /> -->
        <div class="row  w-100 align-items-center justify-content-center">
             <div class="col-12">
            <img src="/img/logo.png" alt="Logo da empresa" class="spinner" >
        </div>
        <div class="col-12 mt-3">
            <h4>Carregando...</h4>
        </div>
        </div>
       
  </div>
</template>

<script>

export default {
  name: "loadingscreen",
  props: ["isloading"],
//   components: {
//         LoadSpinnerVue

//   }
};
</script>

<style scoped>

img{
    width: 50px !important;
    height: 50px !important;
}


.spinner{
  width: 100px;
  height: 100px;
  animation: rotate 2s linear infinite;
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.loader {
  z-index: 999;
  background-color: #161616;
  bottom: 0;
  color: white;
  display: block;
  font-size: 32px;
  left: 0;
  overflow: hidden;
  padding-top: 10vh;
  position: fixed;
  right: 0;
  text-align: center;
  top: 0;
}

.fadeout {
  animation: fadeout 0.2s forwards;
}

@keyframes fadeout {
  to {
    opacity: 0;
    visibility: hidden;
  }
}
</style>