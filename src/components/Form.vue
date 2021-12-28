<template>
  <form v-for="movie in movies">
    <h3>{{ movie.name }}</h3>

    <button
      type="button"
      v-on:click="movie.quantity -= 1"
      disabled="{ movie.quantity < 0 }"
    >
      -
    </button>

    {{ movie.quantity }}

    <button
      type="button"
      v-on:click="movie.quantity += movie.available"
      disabled="{ movie.quantity > movie.available }"
    >
      +
    </button>
  </form>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      movies: [
        {
          name: "Avengers",
          available: 3,
          quantity: 0,
        },
        {
          name: "Transformers",
          available: 6,
          quantity: 0,
        },
        {
          name: "Matrix",
          available: 7,
          quantity: 0,
        },
        {
          name: "Ice Age",
          available: 9,
          quantity: 0,
        },
        {
          name: "Act Age",
          available: 3,
          quantity: 0,
        },
        {
          name: "Star Wars",
          available: 11,
          quantity: 0,
        },
      ],
    };
  },
};
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
