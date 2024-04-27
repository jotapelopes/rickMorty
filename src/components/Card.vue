<style>
  .container{
    display: inline-flex;
    width: 1500px;
  }
</style>

<template>
  <main>
    <div class="container">
      <div v-for="character in characters" :key="character.id">
        <div class="card" style="width: 18rem;">
            <img :src="character.image" class="card-img-top" :alt="character.name">
            <div class="card-body">
              <h5 class="card-title"> {{ character.name }} </h5>
              <ul class="list-group list-group-flush">
                <li class="list-group-item"><b>Status: </b> {{ character.status }}</li>
                <li class="list-group-item"><b>Especie: </b> {{ character.species }}</li>
                <li class="list-group-item"><b>Genêro: </b> {{ character.gender }}</li>
                <li class="list-group-item"><b>Localização atual: </b> {{ character.location.name }}</li>
                <li class="list-group-item"><b>Qtde de ep que aparece: </b> {{ character.episode.length }}</li>
              </ul>
            </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
        characters: [],
        error: null
    };
  },
  mounted() {
      axios
      .get('https://rickandmortyapi.com/api/character')
      .then(response => {
        this.characters = response.data.results;
      })
      .catch(error => {
        this.error = error;
      });
  }
}
</script>
