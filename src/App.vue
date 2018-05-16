<template>
  <div id="app">
    <card></card>
    <card></card>
    <card></card>
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
#app {

}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
