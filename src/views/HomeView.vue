<script setup>
import { onMounted, reactive, ref, computed } from "vue";
import PokemonsList from "../components/PokemonsList.vue";
import PokemonCard from "../components/PokemonCard.vue";

let pokemons = reactive(ref());
let urlBaseSvg = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/");
let urlBaseType = ref("https://pokeapi.co/api/v2/type/")
let searchPokemon = ref("");
let pokemonSelected = reactive(ref());
let loading = ref(false);
let i = 0;

onMounted(() => {
  fetch("https://pokeapi.co/api/v2/pokemon?limit=10000&offset=0")
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

const selectPokemon = async (pokemon)=>{
  loading.value = true;
  await fetch(pokemon.url)
  .then(res => res.json())
  .then(res => pokemonSelected.value = res)
  .catch(err => alert(err))
  .finally(()=> loading.value = false)

  console.log(pokemonSelected.value);
};

</script>

<template>
  <main>
    <div class="conteiner">
      <div class="row m-4 p-2">
        <div class="col-sm-12 col-md-6">
          <PokemonCard 
          :name="pokemonSelected?.name"
          :xp="pokemonSelected?.base_experience"
          :height="pokemonSelected?.height"
          :image = "pokemonSelected?.sprites.other.dream_world.front_default"
          :loading="loading"
          :type1="pokemonSelected?.types[0].type.name"
          :type2="pokemonSelected?.types[1].type.name"
          :weight:="pokemonSelected?.weight"
          />
        </div>

        <div class="col-sm-12 col-md-6">
          <div class="card list">
            <div class="card_body row">
              <div class="mb-3">
                <label hidden for="searchPokemon" class="form-label">
                  Pesquisar Pokemon.
                </label>

                <input v-model="searchPokemon" type="text" class="form-control" id="searchPokemon"
                  placeholder="Who's that Pokemon? (Pesquisar Pokemon)">
              </div>

              <PokemonsList v-for="pokemon in pokemonsFilter" :key="pokemon.name" :name="pokemon.name"
                :urlBaseSvg="urlBaseSvg + pokemon.url.split('/')[6] + '.svg'" 
                @click="selectPokemon(pokemon)"
                />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.list{
  max-height: 85vh;
  overflow-y: scroll;
  overflow-x: hidden;
  scrollbar-color: rgb(255, 0, 0) rgb(255, 173, 173);
  scrollbar-gutter: stable both-edges;
  scrollbar-width: thin;
}
</style>