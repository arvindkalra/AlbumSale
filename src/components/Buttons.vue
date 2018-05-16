<template>
<div class="buttonBox">
  <div class="initialButtons columns is-mobile">
    <div class="column has-text-centered">
      <a class="button is-danger is-outlined">Remove</a>
    </div>
    <div class="column has-text-centered">
      <a class="button is-success is-outlined">Buy Now</a>
    </div>
  </div>
  <div class="finalButton">

  </div>
</div>
</template>

<script>
    export default {
        name: "Buttons"
    }
</script>

<style scoped>
.button{
  width: 100%;
}
  .buttonBox{
    margin: 12px;
  }
</style>
