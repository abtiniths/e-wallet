<template>
  <main id="app">
<Home  v-if="page.Home"
      :cards="cards"
      :currentCard="currentCard"
      v-on:toggleScreens="page.Home = !page.Home"
      v-on:setCurrentCard="setCurrentCard"
 />
<AddCard  v-if="!page.Home"
          v-on:toggleScreens="page.Home = !page.Home"
          v-on:addCard="addCard"
 />
 
 
  </main>
</template>

<script>
import Home from "./components/Home"
import AddCard from "./components/AddCard"
export default {
name: 'App',
components: {
  Home,
  AddCard,
},
data() {
  return {
    page: {Home:true},
    cards : [
         {
          vendor: "bitcoin", 
          cardNumber: "53123213214", 
          cardHolder: "first stuffesson", 
          expireMonth: "01/01", 
          expireYear: "01/01", 
          CCV:"223"
        },
         {
          vendor: "blockchain", 
          cardNumber: "53123213214", 
          cardHolder: "sec stuffesson", 
          expireMonth: "01/01", 
          expireYear: "01/01", 
          CCV:"223"
        },
         {
          vendor: "evil", 
          cardNumber: "53123213214", 
          cardHolder: "third stuffesson", 
          expireMonth: "01/01", 
          expireYear: "01/01", 
          CCV:"223"
        },
   
     ],
     currentCard: {
         
          vendor: 'Blank', 
          cardNumber: "53123213214", 
          cardHolder: "stuff stuffesson", 
          expireMonth: "01/01", 
          expireYear: "01/01", 
          CCV:"223"
        }
  }},

methods: {
  addCard(card) {
    this.cards.push(card)
  },
  setCurrentCard (card) {
    this.currentCard = card
  }
}

}




</script>




<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  color: #2c3e50;
  margin-top: 1rem;
}
.ol{
  display: flex;
  flex-direction: column;
  margin: 100 px
}
</style>