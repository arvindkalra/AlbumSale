<template>
  <div id="app">
    <a class="button is-danger is-outlined is-size-4">A &nbsp; L &nbsp; B &nbsp; U &nbsp; M &nbsp; S</a>
    <div class="columns" v-for="innerList in list">
      <div class="column" v-for="element in innerList">
        <card v-bind:title="element.title"
              v-bind:artist="element.artist"
              v-bind:thumbnail="element.thumbnail_image"
              v-bind:url="element.url"
              v-bind:image="element.image"></card>
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
  data(){
    return {
      chunkSize : 3,
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
        let index = 0;
        let arrayLength = myArray.length;
        let chunk_size = this.chunkSize;

        for (index = 0; index < arrayLength; index += chunk_size) {
          let myChunk = myArray.slice(index, index+chunk_size);
          this.list.push(myChunk);
        }
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
