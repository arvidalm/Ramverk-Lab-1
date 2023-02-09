<!-- a component for the logo-->
<template>
  <div class="logo-container">
    <img
      id="logo"
      src="src/assets/images/swlogo.png"
      alt="The sickest logo youve ever seen"
      width="200"
      height="200"
      class="image"
    />
  </div>
</template>

<style scoped>
.logo-container {
  display: flex;
  justify-content: center;
  margin-top: 2rem;
}

.image {
  width: 400px;
  height: 200px;
}
</style>
