<script setup>
const pokemon = defineProps(["name", "xp", "height", "image", "loading"]);

</script>

<template>
  <div class="card CardPokemonSelected" :class="loading ? '' : 'animate__animated animate__flipInY'">
    <img v-if="pokemon.name"
    :src="pokemon.image"
    class="card-img-top-loading p-5" :alt="pokemon.name">
    <img 
    v-else
    src="../assets/images/pokeball.png"
    class="card-img-top p-5" alt='Who is that pokemon?'>
    <div class="card-Pokemon-selected">
      <h5 class="card-title text-center">{{ pokemon.name || "Who is that pokemon?"}}</h5>
      <hr>
      <div class="row">
        <section class="col">
          <strong>XP: </strong>
          <span>{{ pokemon.xp }}</span>
        </section>
        <section class="col">
          <strong>Altura : </strong>
          <span>{{ pokemon.height }}</span>
        </section>
      </div>
    </div>
  </div>
</template>

<style>
.card-Pokemon-selected {
  padding-bottom: 5rem;
  max-height: 85vh;
  /* overflow-y: scroll; */
  overflow-x: hidden;
  scrollbar-color: rgb(255, 0, 0) rgb(255, 173, 173);
  scrollbar-gutter: stable both-edges;
  scrollbar-width: thin;
}

.col{
  margin-left: 1.5rem;
}




</style>