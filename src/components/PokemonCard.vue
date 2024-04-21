<script setup>
const pokemon = defineProps(["name", "xp", "height", "image", "loading", "type1", "type2", "weight"]);

</script>

<template>
  <div class="card CardPokemonSelected" :class="loading ? '' : 'animate__animated animate__flipInY'"
    v-if="pokemon.name">
    <img :src="pokemon.image" class="card-img-top-loading p-5" :alt="pokemon.name">
    <div class="card-Pokemon-selected">
      <h5 class="card-title text-center">{{ pokemon.name || "Who is that pokemon?" }}</h5>
      <hr>
      <div class="row">
        <div class="col">
          <p><strong>Tipo:</strong></p>
          <div>
            <v-card class="type">{{ pokemon.type1 }}</v-card>
            <v-card class="type"> {{ pokemon.type2 }}</v-card>
          </div>
        </div>
        <section class="col">
          <strong>XP: </strong>
          <span>{{ pokemon.xp }}</span>
        </section>
        <section class="col">
          <strong>Altura : </strong>
          <span>{{ pokemon.height }}</span>
          <hr>
          <strong>Peso: </strong>
          <span>{{ pokemon.weight }}</span>
        </section>
      </div>
    </div>
  </div>
  <div v-else>
    <img src="../assets/images/pokeball.png" class="card-img-top p-5" alt='Who is that pokemon?'>
    <h5 class="card-title text-center">{{ pokemon.name || "Who is that pokemon?" }}</h5>
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

.col {
  margin-left: 1.5rem;
}

.type {
  background: rgb(255, 176, 176);
  padding: 0.5rem;
  margin-top: 1rem;
  border-radius: 16px;
  display: flex;
  justify-content: center;
}
</style>