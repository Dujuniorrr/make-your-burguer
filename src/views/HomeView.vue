<script setup>

</script>

<template>
  <BannerComponent />
  <div class="container mt-3">
    <h1 class=" text-center ">Monte o seu burguer:</h1>
    <BurguerFormComponent />
  </div>
</template>

<script>
import BannerComponent from '../components/partials/Banner.vue'
import BurguerFormComponent from '../components/forms/BurguerForm.vue'

export default {
  components: {
    BannerComponent,
    BurguerFormComponent
  }
}
</script>
