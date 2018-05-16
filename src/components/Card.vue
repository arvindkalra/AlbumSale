<template>
    <div class="card">
      <head-in-card v-bind:title="title"
                    v-bind:artist="artist"
                    v-bind:thumbnail="thumbnail"
                    v-on:remove="remove"></head-in-card>

      <imageBox v-bind:image="image"></imageBox>
      <buttons v-bind:url="url"
               v-on:remove="remove"></buttons>
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
        },
        props: [
          "title",
          "artist",
          "thumbnail",
          "image",
          "url",
          "index"
        ],
        events: ["remove"],
        methods: {
          remove(){
            this.$emit('removeCard', {index : this.index});
          }
        }
    }
</script>

<style scoped>
  .card{
  }
</style>
