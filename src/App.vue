<script setup>
import {ref} from 'vue'

let num = ref(0)

</script>

<script setup>

</script>

<template>
  <!-- NAVIGATION BAR -->
  <nav class="navbar navbar-expand-lg navbar-dark bg-danger">
    <div class="container-fluid">
      <router-link class="navbar-brand d-flex" to="/">
        <img src="./assets/images/pokeball.png" alt="" height="40" class="pokeball-img d-inline align-text-center text-white m-2">
        <h1 class="pokedex-title mx-2">Pokedex</h1>
      </router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link text-white" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link text-white" to="/about">Sobre a Pokedex</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <div class="main">
    <router-view></router-view>

  </div>
 

  <footer class="bg-danger text-white">
    <div>
      Desenvolvido por Stephanie Souza
    </div>
  </footer>
</template>

<style>
footer{
  position: fixed;
  bottom: 0;
  width: 100%;
  display: flex;
  align-items:center;
  justify-content: center;
  height: 56px;
}

.pokedex-title{
  font-family:'Pokemon Solid', sans-serif;
  font-size: 2.2rem;
}

.container-fluid{
  display: flex;
  align-content: flex-start;
}
</style>