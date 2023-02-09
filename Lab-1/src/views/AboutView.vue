<script setup>
import NavBar from "../components/NavBar.vue";
import LogoComponent from "../components/LogoComponent.vue";
import QuestionComp from "../components/QuestionComp.vue";
import CustomEvent from "../components/CustomEvent.vue";
import StarProp from "../components/StarProp.vue";
</script>

<template>
  <NavBar></NavBar>
  <LogoComponent></LogoComponent>
  <div class="text-block">
    <p>This page is for extremely important information</p>
  </div>
  <QuestionComp></QuestionComp>
  <div>
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
  <StarProp :Year="1977" :Quote="'No... I, am your father.'" />
  <custom-event @custom-event="handleCustomEvent"></custom-event>
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
