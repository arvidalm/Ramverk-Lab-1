<script setup>
import NavBar from "../components/NavBar.vue";
import LogoComponent from "../components/LogoComponent.vue";
</script>

<template>
  <NavBar></NavBar>
  <LogoComponent></LogoComponent>
  <div class="text-block">
    <p>This page is for extremely important information</p>
  </div>
  <div>
    <div>
      <p style="color: white">Whos your favourite character?</p>
      <form>
        <input type="text" v-model="inputValue" />
      </form>
      <button @click="showResult = true">Submit your fav character!</button>
      <p style="color: white" v-if="showResult">
        Are you kidding me? {{ inputValue }} is the worst character ever and
        almost ruined the franchise. Shame.
      </p>
    </div>
    <div class="card-container">
      <div class="card">
        <img
          src="src/assets/images/vader.jpg"
          alt="Me and my friend and Lord Vader"
        />
        <p>Me and my friend and Darth Vader, Dark Lord of the Sith :)</p>
      </div>
      <div class="card">
        <img
          src="src/assets/images/nihilus.jpg"
          alt="Me and my friend and Lord Nihilus"
        />
        <p>Me and my friend and Darth Nihilus, pretty cool guy :)</p>
      </div>
    </div>
  </div>
  <!-- props -->
  <StarProp
    :number="1977"
    :message="'Was the year the first Star Wars movie was released'"
  />
  <custom-event @custom-event="handleCustomEvent"></custom-event>
</template>

<script>
import CustomEvent from "../components/CustomEvent.vue";
import StarProp from "../components/StarProp.vue";
export default {
  data() {
    return {
      inputValue: "",
      showResult: false,
    };
  },
  methods: {
    handleCustomEvent(data) {
      console.log(data.message);
    },
  },
};
</script>

<style>
.card-container {
  display: flex;
  justify-content: center;
}

.card {
  width: 300px;
  height: 250px;
  margin: 20px;
  text-align: center;
}

.card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}
</style>
