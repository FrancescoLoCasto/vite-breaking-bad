
<script>
import AppCard from './AppCard.vue'
import { store } from '../store.js'
import AppSelectCard from "./AppSelectCard.vue";
import axios from "axios";

export default {
   components:{
      AppCard,
      AppSelectCard
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

<div class="select-container">
      <AppSelectCard @getCardsType="getCardsType(store.selecType)"/>
</div>

<div class="container-bg">
      <div class="box-card">
         <div class="card">
            <AppCard  v-for="card in store.listCard" :cardElement="card" />
         </div>
      </div>
</div>
</template>


<style lang="scss" scoped>
   .container-bg{
      padding: 2rem;
      background-color: #a6b5a3;

         .box-card{
            width: calc(100%);
            text-align: center;
            display: flex;
            flex-wrap: wrap;


         }
   }
</style>