<template>
  <div>
    <button @click="fetchCharacters">Fetch Characters</button>
    <div v-if="loading">Loading...</div>
    <div v-else>
      <div class="character-cards">
        <div
          class="character-card"
          v-for="(character, index) in characters"
          :key="index"
        >
          <h2>{{ character.name }}</h2>
          <p>Homeworld: {{ character.homeworld }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.character-cards {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
.character-card {
  width: 200px;
  margin: 10px;
  text-align: center;
}
</style>

<script>
import axios from "axios";

export default {
  data() {
    return {
      characters: [],
      loading: false,
    };
  },
  methods: {
    fetchCharacters() {
      this.loading = true;
      const promises = [];
      for (let i = 0; i < 10; i++) {
        const randomNumber = Math.floor(Math.random() * 88) + 1;
        promises.push(
          axios.get(`https://swapi.dev/api/people/${randomNumber}/`)
        );
      }
      axios
        .all(promises)
        .then((responses) => {
          this.characters = responses.map((response) => ({
            ...response.data,
          }));
          return axios.all(
            this.characters.map((character) => axios.get(character.homeworld))
          );
        })
        .then((homeworldResponses) => {
          this.characters.forEach((character, index) => {
            character.homeworld = homeworldResponses[index].data.name;
          });
          this.loading = false;
        })
        .catch((error) => {
          console.error(error);
          this.loading = false;
        });
    },
  },
};
</script>
