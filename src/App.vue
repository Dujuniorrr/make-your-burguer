<template>

  <SplashScreenComponent :isloading="isloading" />
  <div v-show="!isloading">
     <NavbarComponent />

  <main>
    <div class="content-wrap">
      <RouterView />
    </div>
  </main>

  <FooterComponent  />
  </div>

</template>

<script>
import NavbarComponent from "./components/partials/Navbar.vue";
import FooterComponent from './components/partials/Footer.vue';
import SplashScreenComponent from './components/apresentation/SplashScreen.vue';

export default{
  name: 'App',
  components: {
    NavbarComponent,
    FooterComponent,
    SplashScreenComponent

  },
  data(){
    return {
      isloading: true
    }
  },
  created(){
    setTimeout(() => {
      console.log("carregou")
      this.isloading = false;
    }, 2000);
  }
}
</script>

<style>
body{
  min-width: 370px;
}
 main {
  position: relative;
  min-height: 100vh;
}

#content-wrap {
  padding-bottom: 2.5rem;    /* Footer height */
}

</style>