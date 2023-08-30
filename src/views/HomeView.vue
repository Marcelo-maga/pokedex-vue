<script setup>
  import { onMounted, reactive, ref } from 'vue';
  import ListPokemons from '@/components/ListPokemons.vue';

  let pokemons = reactive(ref());

  onMounted(() => {
    fetch('https://pokeapi.co/api/v2/pokemon/?limit=20&offset=0')
      .then((response) => response.json())
      .then(response => {
        pokemons.value = response.results;
        console.log(response);
      })
  }) 
</script>

<template>
  <main>

    <div class="col-sm-12 col-md-6">
      <div class="card">
        <div class="card-body row">
          <ListPokemons v-for="pokemon in pokemons" :key="pokemon.name" :name="pokemon.name" :url="pokemon.url" />
        </div>
      </div>
    </div>

  </main>
</template>
