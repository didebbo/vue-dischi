<template>
  <header>
    <a href="#">
      <img src="/images/spotify-logo.png" alt="Spotify" class="logo" />
    </a>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped lang="scss">
@import "../scss/colors";
header {
  background-color: $color-header;
  padding: 0.5em 1em;

  .logo {
    height: 2em;
  }
}
</style>