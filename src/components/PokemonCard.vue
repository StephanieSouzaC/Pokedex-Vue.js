<script setup>
const pokemon = defineProps(["name", "xp", "height", "image", "loading", "type1", "type2", "weight", "moves"]);

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
          <strong>Altura : </strong>
          <span>{{ pokemon.height }}</span>
          <hr>
          <strong>Peso: </strong>
          <span>{{ pokemon.weight }}</span>
          <hr>
        <strong>XP: </strong>
          <span>{{ pokemon.xp }}</span>
        </section>
      <div class="moves">
        <strong class="titleMoves">Movimentos de Ataque: </strong>  
        <ul class="movesList">
            <li v-for="move in moves" :key="move.move.name">{{ move.move.name }}</li>
          </ul>
      </div>
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

.moves {
  display: flex;
  flex-wrap: wrap;
  margin: 1rem;
  padding: 1rem;
}

.movesList {
  list-style-type: none;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
}

.movesList li{
  flex-basis: calc(33.33% - 10px);
  margin-right: 10px;
  margin-bottom: 10px;
}
.titleMoves {
  width: 100%;
  padding-bottom: 1rem;
}
</style>