<script setup>
const pokemon = defineProps(["name", "xp", "height", "image"]);

</script>

<template>
<div class="card-Pokemon-selected">
    <img :src="pokemon.image" weigth="150" height="280" class="card-img-top p-3" :alt="pokemon.name">
    <div class="card-Pokemon-selected">
      <h5 class="card-title text-center">{{pokemon.name}}</h5>
      <hr>
      <div class="row">
        <section class="col">
            <strong>XP: </strong>
            <span>{{pokemon.xp}}</span>
        </section>
        <section class="col">
            <strong>Altura(cm) : </strong>
            <span>{{ pokemon.height }}</span>
        </section>
      </div>
    </div>
  </div>
</template>

<style>
.card-Pokemon-selected{
    height: 50rem;
}
</style>