<template>
  <input
    type="button"
    :value="$store.state.counter"
    @click="$store.commit('increment')"
  />
</template>
<!-- button to increase a value saved in VueX -->

<!-- very simple -->
