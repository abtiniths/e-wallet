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
         <select
       name="Year"
       class="card-month"
       v-model="card.expireYear"
       @change="createCard"
       >
            <option value="22">22</option>
            <option value="23">23</option>
            <option value="24">24</option>
            <option value="25">25</option>
            <option value="26">21</option>
         </select>
        
       <select
       name="Month"
       class="card-month"
       v-model="card.expireMonth"
       @change="createCard"
       >
        <option value="01">01</option>
        <option value="02">02</option>
        <option value="03">03</option>
        <option value="04">04</option>
        <option value="05">05</option>
        <option value="06">06</option>
        <option value="07">07</option>
        <option value="08">08</option>
        <option value="09">09</option>
        <option value="10">10</option>
        <option value="11">11</option>
        <option value="12">12</option>
       </select>
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
   
  },
data() {
  return {
    
    card : {
      vendor: '',
      cardHolder: '',
      cardNumber: '',
      expireYear: '',
      expireMonth: '',
    
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
      expireMonth: this.card.expireMonth
    
    }
    this.$emit('createCard', card)
  },
}
}
</script>

<style lang="scss" scoped>


input, label {
    display:block;
}


label {
  margin-bottom: -14px;
  font-family: "PT Mono";
  font-size: 10px;
  color: rgba(0, 0, 0, 0.8);
  text-transform: uppercase;
}
.card-name-input {
  font-family: "PT Mono";
  margin: 14px 0;
  text-align: center;
  width: 382px;
  font-size: 15px;
  height: 40px;
  border-radius: 8px;
  border-color: rgba(0, 0, 0, 0.8);
  border-width: 1px;
  outline: none;
}

 .card-number-input {
  font-family: "PT Mono";
  margin: 14px 0;
  text-align: center;
  width: 382px;
  font-size: 15px;
  height: 40px;
  border-radius: 8px;
  border-color: rgba(0, 0, 0, 0.8);
  border-width: 1px;
 
}
.card-year-input{
font-family: "PT Mono";
  margin: 14px 0;
  text-align: center;
  width: 140px;
  font-size: 15px;
  height: 40px;
  border-radius: 8px;
  border-color: rgba(0, 0, 0, 0.8);
  border-width: 1px;
  
  
}
.card-year{
  display: flex;
  flex-direction: row;
  
}
.card-month{
  font-family: "PT Mono";
  margin: 14px 0;
  text-align: center;
  width: 140px;
  font-size: 15px;
  height: 40px;
  border-radius: 8px;
  border-color: rgba(0, 0, 0, 0.8);
  border-width: 1px;
  outline: none;
}


input::placeholder {
  font-size: 15px;
  font-family: "PT Mono";
  text-align: center;
}
.card_form {
  margin-top: 20px;
  height: 200px;
  padding: 1rem;
  width: 382px;
}
select{ 
 width: 382px;
  height: 42px;
  border-radius: 8px;
  border-color: rgba(0, 0, 0, 0.8);
  border-width: 1px;
  outline: none;
  background-color: white;
  padding: 8px 15px;

  &:after {
    content:"";
    width: 0;
    height: 0;
    border: 7px solid transparent;
   
    position: absolute;
    top: 16px;
    right: 10px;
  }
  &:hover {
    background-color:bisque
  }
  &:active, &.active {
      background-color:rgb(182, 182, 150);
    &:after {
      top: 9px;
      
    }
  }
}

</style>