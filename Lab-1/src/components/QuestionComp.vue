<template>
  <div>
    <p style="color: white">Who's your favorite character?</p>
    <form>
      <input type="text" v-model="inputValue" />
    </form>
    <button @click="submitForm">Submit your fav character!</button>
    <p style="color: white" v-if="showResult">
      {{ specialMessage() }}
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputValue: "",
      showResult: false,
    };
  },
  methods: {
    submitForm() {
      this.showResult = true;
    },
    specialMessage() {
      if (this.inputValue === "Arvid" || this.inputValue === "Damir") {
        return `I 100% agree. ${this.inputValue} is the highlight of the movies and saved the franchise`;
      } else {
        return `Are you kidding me? ${this.inputValue} is the worst character ever and almost ruined the franchise. Shame.`;
      }
    },
  },
};
</script>
