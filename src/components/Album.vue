<template>
  <div class="album">
    <div class="inner">
      <div class="thumb">
        <a href="#">
          <img :src="data.poster" :alt="data.title" />
        </a>
      </div>
      <div class="info">
        <div class="title">
          <h6>
            <a href="#">
              {{ data.title }}
            </a>
          </h6>
        </div>
        <div class="desc">
          <span class="author">
            <a href="#">
              {{ data.author }}
            </a>
          </span>
          <span class="year">
            <a href="#">
              {{ data.year }}
            </a>
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

  a {
    color: $color-light-text;
    text-decoration: none;
  }

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

      a {
        display: flex;

        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
          object-position: center;
        }
      }
    }
    .info {
      display: flex;
      flex-direction: column;
      text-align: center;
      justify-content: center;
      flex-grow: 1;
      .title {
        margin: 1em 0 0 0;
        text-transform: uppercase;
      }
      .desc {
        opacity: 0.4;
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