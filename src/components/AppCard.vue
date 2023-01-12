
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

   }
   
}
</script>


<template lang="">
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