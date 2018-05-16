<template>
  <figure class="image is-1by1">
    <img :src="image">
  </figure>
</template>

<script>
    export default {
        name: "ImageBox",
        props: ["image"]
    }
</script>

<style scoped>
.image{
  margin: 12px;
}
</style>
