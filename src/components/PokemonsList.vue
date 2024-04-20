<script setup>
const pokemon = defineProps(["name", "urlBaseSvg"])

</script>

<template>
    <div class="col-4">
        <div class="card mb-3 p-2 cardPokemonList">
            <p class="text-center">{{ pokemon.name }}</p>
            <img 
            :src="urlBaseSvg" class="card-img-top" 
            alt="..."
            height="82"
            />
        </div>
    </div>
</template>

<style scoped>

.cardPokemonList{
    background-color: rgb(255, 233, 235);
    background: radial-gradient(circle, rgba(255, 0, 0, 0.432) 2%, rgba(255, 255, 255, 0.877) 100%);
    cursor: pointer;
}

.cardPokemonList img:hover{
    padding: .2rem;
}
</style>