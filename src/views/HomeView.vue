<script setup>
import { onMounted, reactive, ref, computed } from "vue";
import PokemonsList from "../components/PokemonsList.vue";

let pokemons = reactive(ref());
let urlBaseSvg = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/");
let searchPokemon = ref("");

onMounted(() => {
  fetch("https://pokeapi.co/api/v2/pokemon?limit=1000&offset=0")
    .then(res => res.json())
    .then(res => pokemons.value = res.results);
});

const pokemonsFilter = computed(()=>{
  if(pokemons.value && searchPokemon.value){
    return pokemons.value.filter(pokemon=>
  pokemon.name.toLowerCase().includes(searchPokemon.value.toLowerCase()))
  }
  return(pokemons.value);
});

</script>

<template>
  <main>
    <div class="conteiner">
      <div class="row m-4 p-2">
        <div class="col-sm-12 col-md-6">
          <div class="card">
            <img src="..." class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Card title</h5>
              <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's
                content.</p>
            </div>
          </div>

        </div>

        <div class="col-sm-12 col-md-6">
          <div class="card">
            <div class="card_body row">
              <div class="mb-3">
                <label hidden for="searchPokemon" class="form-label">
                  Pesquisar Pokemon.
                </label>

                <input v-model="searchPokemon" type="text" class="form-control" id="searchPokemon"
                  placeholder="Who's that Pokemon? (Pesquisar Pokemon)">
              </div>

              <PokemonsList v-for="pokemon in pokemonsFilter" :key="pokemon.name" :name="pokemon.name"
                :urlBaseSvg="urlBaseSvg + pokemon.url.split('/')[6] + '.svg'" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style></style>