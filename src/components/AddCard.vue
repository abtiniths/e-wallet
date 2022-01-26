<template>
  <div id="add-card">
    <header>
         <Header title=" addcard title"  :cardMode="cardMode" />
         <Card :cardInfo="card" v-model="card" />
         <CardForm @createCard="createCard" v-model="card"/>
         <button class="btn-add-card" @click="addCard">Add</button>
           
     </header>
     </div>
</template>


<script>
import Header from "./Header.vue"
import Card from "./Card.vue"
import CardForm from "./CardForm.vue"
export default {
  name: 'AddCard',
  props:{
    cardInfo : Object
  },
  
  data (){
    return {
    cardMode: 'New',
    
    
    card : {
      vendor: 'blank',
      cardHolder: '',
      cardNumber: '',
      expireMonth: "", 
      expireYear: "",
      }
    }},

  methods: {
    createCard(createdCard){
      this.card = createdCard
    },
    
    addCard() {
      this.$emit('addCard', this.card)
      this.card = {
         vendor: 'Blank',
         cardHolder: '', 
         cardNumber: '',
         expireYear: 'MM/YY'},
      this.$emit('toggleScreens')
    }

  },
  components: {Header, Card, CardForm},
}
    
    
      


</script>



<style>

.btn-add-card{
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