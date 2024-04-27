<style>
  h1{
    text-align: center;
  }
  
  .container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    width: 1500px;
    margin: 0 auto;
  }

  .card {
    flex: 0 0 calc(25% - 20px);
    margin: 10px;
    border-radius: 8.5px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s;
  }

  .card:hover {
    transform: translateY(-5px);
  }


  .card-img-top {
    border-top-left-radius: 8.5px;
    border-top-right-radius: 8.5px;
    object-fit: cover;
    height: 200px;
  }

  .card-body {
    padding: 20px;
  }

  .card-title {
    font-size: 1.25rem;
    margin-bottom: 10px;
  }

  .list-group-item {
    padding: 5px 0;
    font-size: 0.9rem;
  }
</style>

<template>
  <main>
    <h1>Lista de personagens</h1>
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
