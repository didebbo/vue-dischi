<template>
  <header>
    <a href="#">
      <img src="/images/spotify-logo.png" alt="Spotify" class="logo" />
    </a>
    <div class="filters">
      <select @change="filterAuthor" v-model="currentAuthor">
        <option
          v-for="(author, index) in authors"
          :key="index"
          :value="author.value"
        >
          {{ author.label }}
        </option>
      </select>
      <select @change="filterGenre" v-model="currentGenre">
        <option
          v-for="(genre, index) in genres"
          :key="index"
          :value="genre.value"
        >
          {{ genre.label }}
        </option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: ["genres", "authors"],
  data() {
    return {
      currentGenre: "",
      currentAuthor: "",
    };
  },
  watch: {
    genres: function () {
      this.currentGenre = this.genres[0].value;
    },
    authors: function () {
      this.currentAuthor = this.authors[0].value;
    },
  },
  methods: {
    filterGenre() {
      this.$emit("changeGenre", this.currentGenre);
    },
    filterAuthor() {
      this.$emit("changeAuthor", this.currentAuthor);
    },
  },
};
</script>

<style scoped lang="scss">
@import "../scss/colors";
header {
  background-color: $color-header;
  padding: 0.5em 1em;
  display: flex;
  justify-content: space-between;

  .logo {
    height: 2em;
  }
  .filters {
    > * {
      margin: 0 0.4em;
    }
  }
}
</style>