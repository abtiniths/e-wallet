<template>
<div id="home">
  <Header  title="Homeorwhatever"  />
  <p>{{ cards }}s</p>
  </div>
</template>

<script>
import Header from "./Header.vue"
export default {
    
    data() { return {
     cards : [
         {
          vendor: "bitcoin", 
          cardNumber: "53123213214", 
          cardholder: "stuff stuffesson", 
          expireMonth: "01/01", 
          expireYear: "01/01", 
          CCV:"223"
        },
         {
          vendor: "blockchain", 
          cardNumber: "53123213214", 
          cardholder: "stuff stuffesson", 
          expireMonth: "01/01", 
          expireYear: "01/01", 
          CCV:"223"
        },
         {
          vendor: "evil", 
          cardNumber: "53123213214", 
          cardholder: "stuff stuffesson", 
          expireMonth: "01/01", 
          expireYear: "01/01", 
          CCV:"223"
        },
   
     ]
    }
        
    },

components: {Header}
}
</script>

<style>

</style>