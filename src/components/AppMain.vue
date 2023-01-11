
<script>

import { store } from '../store.js'
import axios from "axios";

export default {
   name: 'AppMain',
   data () {
      return{
         store,
      }
   },

   methods: {
      getCard(){
         
      }
   }
}

</script>

<template lang="">
<div class="wrapper-bg">
   <div class="card-container">
      <h1>card</h1>
   </div>
</div>
</template>


<style lang="scss" scoped>
   .wrapper-bg{
      width: 100%;
      height: 100vh;
      background-color: #a6b5a3;

      .card-container{
         margin: 0 auto;
         width: 150vh;
         height: 90vh;
         background-color: white;
      }
   }
</style>