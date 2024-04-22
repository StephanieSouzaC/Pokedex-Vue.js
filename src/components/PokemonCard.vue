<script setup>
const pokemon = defineProps(["name", "xp", "height", "image", "loading", "type1", "type2", "weight", "moves", "id", "evolution", "evolutionName"]);

// const rotate = document.querySelector('pokeball');
// rotate.classList.add('animate__animated', 'animate__rotateIn');

// rotate.addEventListener('animationend', () => {
//   rotate.classList.add('animate__animated', 'animate__rotateIn');
// });
</script>

<template>
  <div class="card CardPokemonSelected" :class="loading ? '' : 'animate__animated animate__flipInY'"
    v-if="pokemon.name">
    <div class="img-card d-flex justify-content-center w-100 h-100">
      <img :src="pokemon.image" class="card-img p-5" :alt="pokemon.name">
    </div>
    <h5 class="card-title text-center">{{ pokemon.name }}</h5>
    <div class="card-Pokemon-selected">
      <hr>
      <div class="row">
        <div class="col">
          <p><strong>Tipo:</strong></p>
          <div>
            <v-card class="type">{{ pokemon.type1 }}</v-card>
            <v-card class="type" id="type2" v-if="pokemon.type2"> {{ pokemon.type2 }}</v-card>
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
        <!-- <section>
            <strong>Evolução: </strong>
            <img :src="pokemon.evolutionName">
            <span>{{ pokemon.evolution}}</span>
          </section> -->

        <div class="moves">
          <strong class="titleMoves">Movimentos de Ataque: </strong>
          <ul class="movesList">
            <li v-for="move in moves" :key="move.move.name">{{ move.move.name }}</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
  <div v-else class="card-not-select p-5 w-100 h-75 text-center">
    <img src="../assets/images/pokeball.png" class="card-img-top poke-animation p-5 w-75 " id="pokeball"
      alt='Who is that pokemon?'>
    <h5 class="card-title-no-Selected text-center">Who is that pokemon?</h5>
  </div>


</template>

<style>
.card-Pokemon-selected {
  padding-bottom: 5rem;
  overflow-x: hidden;
  scrollbar-color: rgb(255, 0, 0) rgb(255, 173, 173);
  scrollbar-gutter: stable both-edges;
  scrollbar-width: thin;
}

.card-img{
  width: 300px;
  height: 300px;
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
  max-height: 34vh;

}

.movesList {
  list-style-type: none;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
}

.movesList li {
  flex-basis: calc(33.33% - 10px);
  margin-right: 10px;
  margin-bottom: 10px;
}

.titleMoves {
  width: 100%;
  padding-bottom: 1rem;
}

.poke-animation {
  animation: captured 1s infinite alternate;
}

@keyframes captured {
  from {
    rotate: 0deg;
  }

  to {
    rotate: 30deg;
  }
}

.card-title-no-Selected {
  font-family: 'Pokemon Solid', sans-serif;
  font-size: 2.5rem;
}
</style>