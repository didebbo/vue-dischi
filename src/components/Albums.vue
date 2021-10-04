<template>
  <div class="container">
    <div class="albums row row-cols-1 row-cols-md-2 row-cols-lg-5">
      <Album
        v-for="(album, index) in filteredAlbums"
        :key="index"
        :data="album"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Album from "./Album.vue";

export default {
  name: "Albums",
  props: ["currentGenre"],
  components: {
    Album,
  },
  data() {
    return {
      albums: [],
      genres: {
        index: ["all"],
        obj: [
          {
            label: "All",
            value: "",
            selected: true,
          },
        ],
      },
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.albums = res.data.response;
        this.albums.forEach((album) => {
          if (!this.genres.index.includes(album.genre.toLowerCase())) {
            this.genres.index.push(album.genre.toLowerCase());
            this.genres.obj.push({
              label: album.genre,
              value: album.genre.toLowerCase(),
              selected: false,
            });
          }
        });
        this.$emit("loadGenres", this.genres.obj);
      });
  },
  computed: {
    filteredAlbums() {
      return this.albums.filter((album) => {
        return album.genre.toLowerCase().includes(this.currentGenre);
      });
    },
  },
};
</script>

<style scoped lang="scss">
@import "./../scss/colors";

.albums {
  color: $color-light-text;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  padding: 1em 0;
}
</style>