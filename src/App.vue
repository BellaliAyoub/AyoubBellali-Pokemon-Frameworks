<template>
  <Logo />

  <Pokemon
    v-for="pokemon in pokemons"
    :pokemonData="pokemon"
    :name="pokemon.name"
    :image="pokemon.url"
  />
</template>

<script setup>
const pokemons = ref();

import { ref } from 'vue';
import Logo from './components/Logo.vue';
import Pokemon from './components/pokemon.vue';
const getPokemons = async function (limit = 12) {
  const data = await fetch(
    `https://pokeapi.co/api/v2/pokemon?limit=${limit}&offset=0`
  ).then((r) => r.json());
  console.log(data);
  pokemons.value = data.results;
  console.log(pokemons);
};
getPokemons();
</script>

<style lang="scss">
.c-logo {
  height: 7rem;
  margin: 2rem auto;
}
</style>
