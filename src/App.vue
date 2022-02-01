<template>
  <main id="app">
<Home  
      v-if="page.Home"
      v-bind:cards="cards"
      v-bind:currentCard="currentCard"
      v-on:toggleScreens="page.Home = !page.Home"
      v-on:setcurrentcard="setCurrentCard"
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
    cards :
     [
         {
          vendor: "bitcoin", 
          cardNumber: "12344567321§", 
          cardHolder: "Hugo Namesson", 
          expireMonth: "01", 
          expireYear: "01", 
          CCV:"223"
        },
         {
          vendor: "blockchain", 
          cardNumber: "234534563456", 
          cardHolder: "Kate Namesson", 
          expireMonth: "01", 
          expireYear: "01", 
          CCV:"223"
        },
         {
          vendor: "evil", 
          cardNumber: "123412343456", 
          cardHolder: "Jackooz Namesson", 
          expireMonth: "01", 
          expireYear: "01", 
          CCV:"223"
        },
   
     ],
     currentCard: {
         
          vendor: 'ninja', 
          cardNumber: "543223455432", 
          cardHolder: "stuff stuffesson", 
          expireMonth: "01", 
          expireYear: "01", 
          CCV:"223"
        },
        
  }},

methods: {
  addCard(card) {
    this.cards.push(card)
    
  },
  setCurrentCard(card) {
    this.currentCard = card
  }
}

}




</script>




<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@200&display=swap');
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  color: #2c3e50;
  margin-top: 1rem;
}

</style>