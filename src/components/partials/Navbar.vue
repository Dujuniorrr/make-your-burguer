
<script>
import { RouterLink, RouterView } from 'vue-router'

export default {
    name: 'Navbar'
}
</script>

<template>
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <div class="container-fluid ">
     <RouterLink to="/" > 
            <img src="public/img/logo.png" alt="Logo com um hámburguer em formato de desenho 2D">
        </RouterLink>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
      <ul class="navbar-nav ">
        <li class="nav-item ">
            <RouterLink to="/" class="nav-link mx-2 p-2 text-warning" aria-current="page">Home</RouterLink>
        </li>
        <li class="nav-item">
            <RouterLink to="/pedidos" class="nav-link mx-2 p-2 text-warning" >Pedidos</RouterLink>
        </li>
      </ul>
    </div>
  </div>
</nav>
</template>

<style scoped>
    img{
        width: 30px;
    }

    .nav-link:hover{
      border-radius: 5px !important;
      transition: transform 0.3s ease-in-out;
    }

    .nav-link:hover{
      background: #ffc107 !important;
      color: black !important;
      transform: scale(1.1);
    }
</style>