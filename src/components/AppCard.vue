
<script>
import { store } from '../store'
import AppSelectCard from "./AppSelectCard.vue";
import axios from "axios"

export default {
   props: {
      cardElement: {
      type : Object,
      required : true
      }
   },

   name: 'AppCard',

   components: {
      AppSelectCard,
   },

   data(){
      return{
         store,
      }
   },

   methods: {
      getCardsType(typeCard){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
         params: {
            archetype: typeCard,
            num: 10,
            offset: 0,
         }
         })
         .then((response) => {
            this.store.cardList = response.data.data
         })
         .catch(function (error) {
            console.log(error)
         })
      }
   },

   create() {
      this.getCardsType(store.selecType);
   }
   
}
</script>


<template lang="">

   <div class="secet-container">
      <AppSelectCard @getCardsType="getCardsType(store.selecType)" />
   </div>

      <div class="card" style="width: 100%;">
        <img :src="cardElement.card_images[0].image_url" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">{{ cardElement.name }}</h5>
          <p class="card-text">{{ cardElement.archetype }}</p>
        </div>
      </div>

</template> 


<style lang="scss">


      .card{
         height: 10rem;
      img{
         height: 25rem;
      }
   }


</style>