<template>
  <div class="album">
    <div class="thumb">
      <img :src="data.poster" :alt="data.title" />
    </div>
    <div class="info">
      <div class="title">
        <h3>
          {{ data.title }}
        </h3>
      </div>
      <div class="author">
        {{ data.author }}
      </div>
      <div class="year">
        {{ data.year }}
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
</style>