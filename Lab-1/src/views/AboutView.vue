<script setup>
import NavBar from "../components/NavBar.vue";
import LogoComponent from "../components/LogoComponent.vue";
</script>

<template>
  <NavBar></NavBar>
  <LogoComponent></LogoComponent>
  <div>
    <nav>
      <!-- Navbar content -->
    </nav>
    <div class="card-container">
      <div class="card">
        <img src="src/assets/images/coruscant.jpg" alt="Image 1" />
        <p>Your text goes here 1.</p>
      </div>
      <div class="card">
        <img src="your-image-2.jpg" alt="Image 2" />
        <p>Your text goes here 2.</p>
      </div>
    </div>
  </div>
</template>

<style>
.card-container {
  display: flex;
  justify-content: center;
}

.card {
  width: 300px;
  height: 400px;
  margin: 20px;
  text-align: center;
}

.card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}
</style>
