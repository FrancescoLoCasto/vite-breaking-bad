
<script>

import { store } from '../store.js'

export default {
   name: "AppSelectCard",
   data() {
      return{
         store,
      }
   },


}
</script>

<template lang="">

   <label for="typeCard">Choose an archetype of card:</label>
   <select name="typeCard" id="typeCard" v-model="store.selectArchetype" @change="$emit('getCard')">
      <option value="Alien">Alien</option>
      <option value="Laval">Laval</option>
      <option value="Vylon">Vylon</option>
      <option value="Inzektor">Inzektor</option>
      <option value="Umi">Umi</option>
      <option value="Gusto">Gusto</option>
   </select>

</template>



<style lang="scss">
   
</style>