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

.btn-home{
position: relative;
width: 382px;
height: 80px;
top: 200px;
border: 1px solid #000000;
box-sizing: border-box;
border-radius: 8px;
font-family: PT Mono;
font-style: normal;
font-weight: bold;
font-size: 22px;
line-height: 25px;
}
.btn-home:hover{
  color: white;
  background-color: black
}
.btn-home:active {
  background-color: #814529;
  box-shadow: 0 5px #666;
  transform: translateY(4px);
}

</style>