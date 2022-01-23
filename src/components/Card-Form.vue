<template>
  <div id="card-form">
      
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