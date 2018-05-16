<template>
    <div class="card">
      <head-in-card></head-in-card>
      <imageBox></imageBox>
      <buttons></buttons>
    </div>
</template>

<script>
  import HeadInCard from './Head-In-Card'
  import ImageBox from './ImageBox'
  import Buttons from "./Buttons"
    export default {
        name: "card",
        components : {
          "head-in-card" : HeadInCard,
          "imageBox": ImageBox,
          "buttons" : Buttons
        }
    }
</script>

<style scoped>
  .card{
  }
</style>
