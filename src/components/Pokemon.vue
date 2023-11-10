<template>
  <p>hallo ik ben {{ pokemonData.name }}</p>
</template>
<script setup>
const props = defineProps({
  pokemonData: {
    type: Object, // {}
    required: true,
  },
});
</script>
<style></style>
