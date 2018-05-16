<template>
  <div id="app">
    <div class="columns">
      <div class="column">
        <card></card>
      </div>
      <div class="column">
        <card></card>
      </div>
      <div class="column">
        <card></card>
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
  }
}
</script>

<style>
.columns{
  margin: 0!important;
}
</style>
