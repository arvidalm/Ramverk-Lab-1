<template>
  <div>
    <button @click="emitCustomEvent">Custom Event Button!!</button>
  </div>
</template>

<script>
export default {
  methods: {
    //custom event that simply console logs a message
    emitCustomEvent() {
      this.$emit("custom-event", { message: "Jar Jar Binks is a sith lord" });
    },
  },
};
</script>
