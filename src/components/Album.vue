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
        <div class="desc">
          <span class="author">
            {{ data.author }}
          </span>
          <span class="year">
            {{ data.year }}
          </span>
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
  padding: 1em;
  display: flex;
  flex-direction: column;
  .inner {
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    padding: 1em;
    background-color: $color-header;

    .thumb {
      display: flex;
      &::after {
        content: "";
        display: block;
        padding-bottom: 100%;
      }

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
      text-align: center;
      .title {
        margin: 1em 0;
        text-transform: uppercase;
      }
      .desc {
        span {
          display: block;
        }
        .year {
          font-size: 0.9em;
        }
      }
    }
  }
}
</style>