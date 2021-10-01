<template>
  <div class="album">
    <div class="inner">
      <div class="thumb">
        <img :src="data.poster" :alt="data.title" />
      </div>
      <div class="info">
        <div class="title">
          <h6>
            {{ data.title }}
          </h6>
        </div>
        <div class="author">
          {{ data.author }}
        </div>
        <div class="year">
          {{ data.year }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Album",
  props: ["data"],
};
</script>

<style scoped lang="scss">
@import "./../scss/colors";
.album {
  // border: 0.2em solid green;
  width: (100% / 5);
  display: flex;
  flex-direction: column;
  padding: 1em;
  .inner {
    padding: 1em;
    background-color: $color-header;

    .thumb {
      display: flex;
      // border: 0.2em solid red;
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
      }
    }
    .info {
      display: flex;
      flex-direction: column;
      align-items: center;
      .title {
        padding: 1em 0;
        text-transform: uppercase;
      }
      .year {
        font-size: 0.9em;
      }
    }
  }
}
</style>