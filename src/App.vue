<template>
  <div id="app">
    <Header :genres="genres" @changeGenre="changeGenre" />
    <main>
      <Albums :currentGenre="currentGenre" @loadGenres="loadGenres" />
    </main>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Albums from "./components/Albums.vue";

export default {
  name: "App",
  components: {
    Header,
    Albums,
  },
  data() {
    return {
      genres: [],
      currentGenre: "",
    };
  },
  methods: {
    loadGenres(genres) {
      this.genres = genres;
    },
    changeGenre(currentGenre) {
      this.currentGenre = currentGenre;
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap");
@import "./scss/colors";
@import "~bootstrap/scss/bootstrap";

body {
  font-family: "Roboto", sans-serif;
  font-size: 1rem;
  cursor: default;
  background-color: $color-body;
}
</style>
