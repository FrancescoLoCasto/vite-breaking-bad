
<script>
import AppCard from './AppCard.vue'
import { store } from '../store.js'
import axios from "axios";

export default {
   components:{
      AppCard
   }, 

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
                  this.store.listCard = response.data.data;
                  console.log(this.store.listCard)
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
<div class="container-bg">
   <div class="card-container">
      <div class="box-card d-flex">
         <AppCard  v-for="card in store.listCard" :cardElement="card" />/>  
      </div>
   </div>
</div>
</template>


<style lang="scss" scoped>
   .container-bg{
      background-color: #a6b5a3;
      display: flex;

      .card-container{
         margin: 0 auto;
         background-color: white;

         .box-card{


         }
      }
   }
</style>