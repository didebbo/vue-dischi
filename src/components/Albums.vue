<template>
  <div class="container">
    <div class="albums row row-cols-1 row-cols-md-2 row-cols-lg-5">
      <Album v-for="(album, index) in albums" :key="index" :data="album" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Album from "./Album.vue";

export default {
  name: "Albums",
  components: {
    Album,
  },
  data() {
    return {
      albums: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.albums = res.data.response;
        // console.log(this.albums);
      });
  },
};
</script>

<style scoped lang="scss">
@import "./../scss/colors";

.albums {
  color: $color-light-text;
  display: flex;
  flex-wrap: wrap;
  padding: 1em 0;
}
</style>