<template>
  <div id="add-card">
    <header>
         <Header title=" addcard title" />
     </header>
     <div class="new-card">
       <label>Card Number</label>
       <input 
       type="text"
       class="card-number-input"
       placeholder="xxxx xxxx xxxx xxxx"
       >
     </div>
        <div class="card-name">
       <label>Cardholder name</label>
       <input 
       type="text"
       class="card-name-input"
       placeholder="FIRSTNAME LASTNAME"
       >
     </div>
        <div class="card-valid">
       <label>Valid thru</label>
       <input 
       type="text"
       class="card-valid"
       placeholder="MM/YY"
       >
     </div>
        <div class="card-ccv">
       <label>CCV Number</label>
       <input 
       type="text"
       class="card-ccv"
       placeholder="###"
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
import Header from "./Header.vue"
export default {
  data (){
    return {

    }
  },



components: {Header}
}
</script>

<style>

</style>