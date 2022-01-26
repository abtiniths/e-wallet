<template>
  <article class="add-card">
      
       <label>Card Number</label>
       <input 
       type="number"
       class="card-number-input"
       placeholder="xxxx xxxx xxxx xxxx"
       v-model="card.cardNumber"
       minlength="16"
       maxlength="16"
       @keyup="createCard"
       >
    
        <div class="card-name">
       <label>Cardholder name</label>
       <input 
       type="text"
       class="card-name-input"
       v-model="card.cardHolder"
       @keyup="createCard"
       placeholder="FIRSTNAME LASTNAME"
       >
     </div>
        <div class="card-year">
       <label>Valid thru</label>
       <input 
       type="number"
       class="card-year"
       @change="createCard"
       placeholder="MM/YY"
       v-model="card.expireYear"
       minlength="5"
       maxlength="5"
       >
       </div>
      

        <div class="card-ccv">
       <label>CCV Number</label>
       <input 
       type="number"
       class="card-ccv"
    
       placeholder="###"
       minlength="3"
       maxlength="3"
       >
     </div>
     <div class="card-vendor">
       <label>Card Vendor</label>
       <select   name="vendor" @change="createCard" v-model="card.vendor">
         <option value="bitcoin">Bitcoin</option>
         <option value="evil">Evil</option>
         <option value="ninja">Ninja</option>
         <option value="blockchain">Blockchain</option>
       </select>
     </div>
      
      </article>
      
      

      
 
 
</template>

<script>
export default {
  name: 'CardForm',
  props: {
    cardInfo: Object
  },
data() {
  return {
    card : {
      vendor: 'Blank',
      cardHolder: '',
      cardNumber: '',
      expireYear: 'YY/MM',
    
    }
  }
},
methods: {
  createCard(){
    let card = {
      vendor: this.card.vendor,
      cardHolder: this.card.cardHolder,
      cardNumber: this.card.cardNumber,
      expireYear: this.card.expireYear,
    
    }
    this.$emit('createCard', card)
  }
}
}
</script>

<style scoped>
.add-card{
  display: flex;
  flex-direction: column;
  margin:150px 25px 150px 25px
}

</style>