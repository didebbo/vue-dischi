<template>
  <div id="app">
    <Header
      :genres="genres"
      :authors="authors"
      @changeGenre="changeGenre"
      @changeAuthor="changeAuthor"
    />
    <main>
      <Albums
        :currentGenre="currentGenre"
        :currentAuthor="currentAuthor"
        @loadGenres="loadGenres"
      />
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
      authors: [],
      currentGenre: "",
      currentAuthor: "",
    };
  },
  methods: {
    loadGenres(obj) {
      this.genres = obj.genres;
      this.authors = obj.authors;
    },
    changeGenre(currentGenre) {
      this.currentGenre = currentGenre;
    },
    changeAuthor(currentAuthor) {
      this.currentAuthor = currentAuthor;
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
