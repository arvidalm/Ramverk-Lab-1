<script setup>
import NavBar from "../components/NavBar.vue";
import LogoComponent from "../components/LogoComponent.vue";
import StarFetch from "../components/StarFetch.vue";
import CounterComp from "../components/CounterComp.vue";
</script>

<template>
  <NavBar></NavBar>
  <CounterComp></CounterComp>
  <p style="color: white">Completely random counter for VueX</p>
  <LogoComponent></LogoComponent>
  <div class="text-block">
    <p>
      This page allows you to fetch 10 Star Wars characters from the SWAPI api!
      Will you get your favourite? <br />
      Also the sequel trilogy sucks I have manually disabled sequel characters
      from appearing here. Such is my hatred for episodes 7, 8 and 9.<br />
      It may take a few seconds for the fetch to work be patient pleas :)
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
