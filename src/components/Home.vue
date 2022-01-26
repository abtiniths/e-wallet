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
#home{
    align-items: center;
}
.btn-home{
position: absolute;
width: 382px;
height: 80px;
left: 770px;
top: 799px;
border: 1px solid #000000;
box-sizing: border-box;
border-radius: 8px;
font-family: PT Mono;
font-style: normal;
font-weight: bold;
font-size: 22px;
line-height: 25px;
}
</style>