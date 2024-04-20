<script setup>
const pokemon = defineProps(["name"])
</script>

<template>
    <div class="col-4">
          <div class="card">
            <p>{{pokemon.name}}</p>
          </div>
        </div>
    <!-- <div class="col-sm-12 col-md-6">
        <div class="card" style="width:18rem;">
            <PokemonsList />
            <ul>
                <li v-for="pokemon in pokemons" :key="pokemon.name">
                    {{ pokemon.name }}
                </li>
            </ul>
        </div>
    </div> -->
</template>

<style></style>