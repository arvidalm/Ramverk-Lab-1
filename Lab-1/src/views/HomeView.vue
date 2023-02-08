<script setup>
import NavBar from "../components/NavBar.vue";
import LogoComponent from "../components/LogoComponent.vue";
import StarFetch from "../components/StarFetch.vue";
</script>

<template>
  <NavBar></NavBar>
  <LogoComponent></LogoComponent>
  <div class="text-block">
    <p>
      This site allows you to fetch 10 Star Wars characters from the SWAPI api!
      Will you get your favourite? <br />
      Also the sequel trilogy sucks I have manually disabled sequel characters from appearing here.
    </p>
  </div>
  <StarFetch></StarFetch>
</template>
<style>
.text-block {
  color: white;
  padding: 20px;
  text-align: center;
}
</style>
