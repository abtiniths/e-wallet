<template>
  <div id="card-stack">
 <Card v-for="(card, index) in cards" 
 :key="index"
 :cardInfo="card" 
 v-on:setcurrentcard="$emit('setcurrentcard', card)"
 />
      
  </div>
</template>

<script>
import Card from"./Card.vue"
export default {
name: 'CardStack',
components: {Card},
props: {
  cards: Array
}
}
</script>

<style scoped>
 #card-stack {
    
     display: grid;
     grid-auto-rows: 5rem;
 
  
 }
 

</style>