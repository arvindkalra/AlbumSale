<template>
<div class="buttonBox">
  <div class="initialButtons columns is-mobile">
    <div class="column left has-text-centered">
      <a class="button is-danger is-outlined">Remove</a>
    </div>
    <div class="column right has-text-centered">
      <a class="button is-success is-outlined">Buy Now</a>
    </div>
  </div>
  <div class="finalButton columns">
    <div class="column">
      <a class="button is-success is-outlined">Confirm</a>
    </div>
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
    margin: 0 12px 0 12px;
  }
  .column{
    padding: .75rem 0 .75rem 0!important;
  }
  .column.left{
    padding-right: 5px!important;
  }
  .column.right{
    padding-left: 5px!important;
  }
  .initialButtons{

  }
  .finalButton{
    display: none;
  }
</style>
