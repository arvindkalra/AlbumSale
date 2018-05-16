<template>
<div class="columns is-mobile head">
  <div class="image-box column is-one-quarter">
    <figure class="image thumbfigure is-1by1">
      <img class=" thumbnail" :src="thumbnail">
    </figure>
  </div>
  <div class="name-box column">
    <div class="is-size-4 is-size-4-mobile">{{title}}</div>
    <div class="is-size-6 is-size-6-mobile">{{artist}}</div>
  </div>
</div>
</template>

<script>
    export default {
        name: "head-in-card",
        props: ["title", "artist", "thumbnail"]
    }
</script>

<style scoped>
  .columns{
    margin: 0!important;
  }
  .thumbnail{
    border-radius: 50%;
  }
  .thumbfigure {
    margin: 0 auto;
  }

  .head{
    box-shadow: 0 0 0 1px rgba(10,10,10,.1);
  }
  .name-box{
    font-family: 'Roboto Condensed', sans-serif;
  }
</style>
