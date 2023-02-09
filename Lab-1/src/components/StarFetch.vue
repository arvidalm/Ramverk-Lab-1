<!-- fetch component -->
<template>
  <p style="color: white">
    You have used the fetch function {{ fetchCount }} times.
  </p>
  <div class="buttonClass">
    <button class="button" @click="fetchCharacters">Fetch Characters</button>
    <div v-if="loading">
      <p style="color: white">Loading...</p>
    </div>
    <!-- print the character cards if they're not still loding -->
    <div v-else>
      <div class="character-cards">
        <div
          class="character-card"
          v-for="(character, index) in characters"
          :key="index"
        >
          <h2 v-bind:title="character.name">{{ character.name }}</h2>
          <p>Homeworld: {{ character.homeworld }}</p>
        </div>
      </div>
    </div>
    <!-- counter for amount of characters fetched processed through computed property  -->
    <p style="color: white">You have fetched {{ characterCount }} characters</p>
  </div>
</template>
<!-- fancy css for fancy cards -->
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
  background-color: white;
}
</style>

<script>
import axios from "axios";

export default {
  data() {
    return {
      characters: [],
      loading: false,
      fetchCount: 0,
    };
  },
  //computed property

  computed: {
    characterCount() {
      return this.characters.length;
    },
  },
  //fetch throgh SWAPI
  methods: {
    fetchCharacters() {
      this.loading = true;
      const promises = [];
      for (let i = 0; i < 10; i++) {
        const randomNumber = Math.floor(Math.random() * 50) + 1;
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
          //find character
          return axios.all(
            this.characters.map((character) => axios.get(character.homeworld))
          );
        })
        //their homeworld
        .then((homeworldResponses) => {
          this.characters.forEach((character, index) => {
            character.homeworld = homeworldResponses[index].data.name;
          });
          this.loading = false;
          this.$emit("fetch-complete");
        })
        .catch((error) => {
          console.error(error);
          this.loading = false;
        });
    },
  },
  //a watch to keep count of many times the user has used the fetch
  watch: {
    loading(newValue) {
      if (!newValue) {
        this.fetchCount++;
      }
    },
  },
};
</script>
