<template>
  <div id="app">
    <a class="button is-danger is-outlined is-size-4">A &nbsp; L &nbsp; B &nbsp; U &nbsp; M &nbsp; S</a>
    <div class="columns">
      <div class="column" v-for="element in list">
        <card v-bind:title="element.title"
              v-bind:artist="element.artist"
              v-bind:thumbnail="element.thumbnail_image"
              v-bind:url="element.url"
              v-bind:image="element.image"
              v-bind:index="element.index"
              v-on:removeCard="onRemoved"></card>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./components/Card"
export default {
  name: 'app',
  components: {
    "card" : Card
  },
  events: ["removeCard"],
  data(){
    return {
      list : []
    }
  },
  mounted() {
    this.getList();
  },
  methods: {
      getList() {
        this.$http.get('https://rallycoding.herokuapp.com/api/music_albums').then(function (response) {
          this.breakArrayIntoChunks(response.data);
        });
      },
      breakArrayIntoChunks(myArray){
        for(let i = 0; i < myArray.length; i++){
          myArray[i].index = i;
        }

        this.list = myArray;
      },
      onRemoved({index}){
        this.list.splice(index, 1);
        this.breakArrayIntoChunks(this.list);
      }
    }
}
</script>

<style>
.columns{
  margin: 0!important;
}
  .button{
    width: 95%;
    margin: 2.5%;
  }
</style>
