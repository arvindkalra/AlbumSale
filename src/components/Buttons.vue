<template>
<div class="buttonBox">
  <div class="initialButtons columns is-mobile" v-bind:style="{display : giveInitialButtonDisplay}">
    <div class="column left has-text-centered">
      <a class="button is-danger is-outlined" v-on:click="removeButtonClicked">Remove</a>
    </div>
    <div class="column right has-text-centered">
      <a class="button is-success is-outlined" v-on:click="bringConfirmButton">Buy Now</a>
    </div>
  </div>
  <div class="finalButton columns"  v-bind:style="{display : giveFinalButtonDisplay}">
    <div class="column">
      <a class="button is-success is-outlined" :href="url">Confirm</a>
    </div>
  </div>
</div>
</template>

<script>
    export default {
        name: "Buttons",
        props: ["url"],
        data(){
          return{
            initialButtonDisplay : "flex",
            finalButtonDisplay : "none"
          };
        },
        computed: {
          giveInitialButtonDisplay(){
            return this.initialButtonDisplay;
          },
          giveFinalButtonDisplay(){
            return this.finalButtonDisplay;
          }
        },
        methods: {
          removeButtonClicked(){
            console.log("Buttons Here");
            this.$emit('remove');
          },
          bringConfirmButton(){
            this.initialButtonDisplay = "none";
            this.finalButtonDisplay = "flex";
          }
        }
    }
</script>

<style scoped>
  .button{
    width: 100%;
    margin: 0;
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
    transition: all 1s linear;
  }
  .finalButton{
    transition: ease-in .5s;
  }
</style>
