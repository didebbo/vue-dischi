<template>
  <div id="app">
    <Header />
    <main>
      <Albums />
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
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap");
@import "./scss/colors";

body {
  font-family: "Roboto", sans-serif;
  font-size: 1rem;
  cursor: default;
}

main {
  background-color: $color-body;
}
</style>
