<template>
  <div id="card-form">
      <div class="new-card">
       <label>Card Number</label>
       <input 
       type="number"
       class="card-number-input"
       placeholder="xxxx xxxx xxxx xxxx"
       v-model="card.cardNumber"
       minlength="16"
       maxlength="16"
       >
     </div>
        <div class="card-name">
       <label>Cardholder name</label>
       <input 
       type="text"
       class="card-name-input"
       v-model="card.cardHolder"
       placeholder="FIRSTNAME LASTNAME"
       >
     </div>
        <div class="card-valid">
       <label>Valid thru</label>
       <input 
       type="number"
       class="card-valid"
       placeholder="MM/YY"
       v-model="card.valid"
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
       <select class="cardVendor">
         <option value="Bitcoin Inc">Bitcoin</option>
         <option value="Evil Corp">Evil</option>
         <option value="Ninja Bank">Ninja</option>
         <option value="Block Chain Inc">Blockchain</option>
       </select>
     </div>
      
      
      

      
  </div>
 
</template>

<script>
export default {
data() {
  return {
    card : {
      vendor: 'Bitcoin',
      cardHolder: '',
      cardNumber: '',
      valid: {
        year: 'YY',
        month: 'MM'
      }
    }
  }
},
methods: {
  createCard(){
    let card = {
      vendor: this.card.vendor,
      cardHolder: this.card.cardHolder,
      cardNumber: this.card.cardNumber,
      valid: this.card.valid
    }
    this.$emit('createCard', card)
  }
}
}
</script>

<style>

</style>