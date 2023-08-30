<script setup>
const pokemon = defineProps(["name", "url"]);
</script>

<template>
  <div class="card" style="width: 18rem">
    <img
      src="https://assets.pokemon.com/assets/cms2/img/pokedex/full/001.png"
      class="card-img-top"
      alt="Imagem Pikachu"
    />
    <div class="card-body">
        <h5 class="card-title">{{ pokemon.name }}</h5>

        <a class="btn btn-success"
            href="{{ pokemon.url }}"
        >
            Ver Detalhes
        </a>

    </div>
  </div>
</template>

<style></style>
