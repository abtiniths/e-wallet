<template>
<div id="home">
  <Header  title="Homeorwhatever" :cardMode="cardMode"/>
  <Card :cardInfo="currentCard" />
  <CardStack :cards="cards"  v-on:setcurrentcard="setCurrentCard" />
  <button class="btn-home" @click="toggleScreens">Add new card</button>
  
  </div>
</template>

<script>
import Header from "./Header.vue"
import Card from "./Card.vue"
import CardStack from "./CardStack.vue"
export default {
name: 'Home',
components: {Header, Card, CardStack},
props: {
  cards: [],
  currentCard: {}
},
  data() { return {
     cardMode: 'active',
    }
        
    },
    methods: {
      toggleScreens() {
        this.$emit('toggleScreens')
      },
      setCurrentCard(card){
        this.$emit('setcurrentcard', card)
      }
    },


}
</script>

<style>

</style>