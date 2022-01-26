<template>
  <div>
    <article class="card" :class="vendorSelect" @click="setCurrentCard">
       <header>
       
        <img v-if="cardInfo.vendor == 'blank'" src="@/assets/chip.svg" alt="chip">
        <img v-if="cardInfo.vendor === 'bitcoin'" src="@/assets/chip.svg" alt="chip">

        <img v-if="cardInfo.vendor !== 'bitcoin'" src="@/assets/wifi_white.svg" alt="wifi">
        <img v-if="cardInfo.vendor == 'bitcoin'" src="@/assets/wifi_white.svg" alt="wifi">
       

        <img v-if="cardInfo.vendor == 'evil'" src="@/assets/evil.svg" alt="Evil Corp">
        <img v-if="cardInfo.vendor == 'evil'" src="@/assets/chip.svg" alt="chip">
        
        <img v-if="cardInfo.vendor == 'blockchain'" src="@/assets/blockchain.svg" alt="Blockchain Inc">
        <img v-if="cardInfo.vendor == 'blockchain'" src="@/assets/chip.svg" alt="chip">

        <img v-if="cardInfo.vendor == 'ninja'" src="@/assets/chip.svg" alt="chip">
        <img v-if="cardInfo.vendor == 'ninja'" src="@/assets/ninja.svg" alt="Ninja Bank">

       
        
      </header>
      <section class="number"> {{cardInfo.cardNumber }} </section>
      <section class="info"> {{ cardInfo.cardHolder }}</section>
      <section class="expireYear"> {{ cardInfo.expireYear}} </section>
     
      </article>

  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    cardInfo: Object
  }
  ,
  data() {
    return {

    }
  },
  methods: {
    setCurrentCard () {
      if (this.cardInfo.vendor == 'blank'){
        this.$emit('setcurrentcard', this.cardInfo)
      }else if (this.cardInfo.vendor == 'evil'){
        this.$emit('setcurrentcard', this.cardInfo)
      }else if (this.cardInfo.vendor == 'bitcoin'){
        this.$emit('setcurrentcard', this.cardInfo)
    }else if (this.cardInfo.vendor == 'blockchain'){
        this.$emit('setcurrentcard', this.cardInfo)
  }}},
  computed: {
    vendorSelect() {
      if (this.cardInfo.vendor === 'bitcoin'){
        return 'bitcoin';
      }else if (this.cardInfo.vendor === 'evil'){
        return 'evil';
      }else if (this.cardInfo.vendor === 'ninja'){
        return 'ninja';
      }else if(this.cardInfo.vendor === 'blockchain'){
        return 'blockchain'
      }else{
        return 'blank'
      }

    }
  },
  

}
</script>

<style>
.card {
    max-width: 400px;
    height: 299px;
    border-radius: black 50px;
    background: #eee;
    padding: 40px;
    box-sizing: border-box;
     
}
.evil {
    background: linear-gradient(248.3deg, rgba(0, 0, 0, 0.16) 0%, rgba(0, 0, 0, 0) 100%), #F33355;
    
    color: white;
}
.blockchain {
    background: linear-gradient(248.52deg, rgba(0, 0, 0, 0.15) 1.49%, rgba(0, 0, 0, 0) 100%), #8B58F9;
    color: white;
}
.bitcoin {
    background: linear-gradient(248.04deg, rgba(255, 255, 255, 0.15) 0%, rgba(255, 255, 255, 0) 99.07%), #FFAE34;
    color: #222;
}
.ninja {
    background: linear-gradient(248.3deg, rgba(255, 255, 255, 0.15) 0%, rgba(255, 255, 255, 0) 100%), #222222;
    color: white;
}
.blank {
    background: linear-gradient(237.75deg, rgba(255, 255, 255, 0.24) 0%, rgba(255, 255, 255, 0) 100%), #D0D0D0;
}

</style>