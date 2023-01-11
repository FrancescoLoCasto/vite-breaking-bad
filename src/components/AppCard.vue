
<script>
import { store } from '../store'
export default {
   props: {
      
      cardElement: {
      type : Object,
      required : true
      }
   },

   data(){
      return{
         store,
      }
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
      img{
         height: 25rem;
      }
   }


</style>