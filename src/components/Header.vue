<template>
  <header>
    <a href="#">
      <img src="/images/spotify-logo.png" alt="Spotify" class="logo" />
    </a>
    <select>
      <option
        v-for="(genre, index) in genres"
        :key="index"
        :value="genre.value"
      >
        {{ genre.label }}
      </option>
    </select>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: ["genres"],
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
}
</style>