
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
         axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0',{
                  params: {
                  }
               })
               .then((response) => {
                  this.test = response.data.data;
                  console.log(this.test)
               })
               .catch(function (error) {
                  console.log(error)
               })
      }
   },

   created() {
      this.getCard();
   }
}

</script>

<template lang="">
<div class="wrapper-bg container">
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