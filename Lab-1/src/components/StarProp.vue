<!-- component for props -->
<template>
  <div>
    <!-- two props -->
    <p style="color: white">Year: {{ Year }}</p>
    <p style="color: white">Quote: {{ Quote }}</p>
    <button @click="logProps">Send the props to the console</button>
  </div>
</template>

<script>
export default {
  //make the props typsäkra hehe
  props: {
    Year: {
      type: Number,
      required: true,
    },
    Quote: {
      type: String,
      required: true,
    },
  },
  methods: {
    //console log the props
    logProps() {
      console.log("Year:", this.Year);
      console.log("Quote:", this.Quote);
    },
  },
};
</script>
