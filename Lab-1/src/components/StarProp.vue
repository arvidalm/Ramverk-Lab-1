<!-- component for props -->
<template>
  <div>
    <!-- two props -->
    <p style="color: white">Number: {{ number }}</p>
    <p style="color: white">Message: {{ message }}</p>
    <button @click="logProps">Send the props to the console</button>
  </div>
</template>

<script>
export default {
  //make the props typsäkra hehe
  props: {
    number: {
      type: Number,
      required: true,
    },
    message: {
      type: String,
      required: true,
    },
  },
  methods: {
    //console log the props
    logProps() {
      console.log("Number:", this.number);
      console.log("Message:", this.message);
    },
  },
};
</script>
