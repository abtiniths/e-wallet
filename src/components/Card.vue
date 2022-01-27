<template>
  <div>
    <article class="card" :class="vendorSelect" @click="setCurrentCard">
       <header>
       
        <img class="bitcoin-logo" v-if="cardInfo.vendor == 'bitcoin'" src="@/assets/bitcoin.svg" alt="bitcoin">

        <img class="blank-chip" v-if="cardInfo.vendor == 'blank'" src="@/assets/chip.svg" alt="chip">
        <img class="bitcoin-chip" v-if="cardInfo.vendor === 'bitcoin'" src="@/assets/chip.svg" alt="chip">

        <img class="wifi" v-if="cardInfo.vendor !== 'bitcoin'" src="@/assets/wifi_white.svg" alt="wifi">
        <img class="bitcoin-wifi" v-if="cardInfo.vendor == 'bitcoin'" src="@/assets/wifi_white.svg" alt="wifi">
       

        <img class="evil-logo" v-if="cardInfo.vendor == 'evil'" src="@/assets/evil.svg" alt="Evil Corp">
        <img class="evil-chip" v-if="cardInfo.vendor == 'evil'" src="@/assets/chip.svg" alt="chip">
        
        <img class="blockchain-logo" v-if="cardInfo.vendor == 'blockchain'" src="@/assets/blockchain.svg" alt="Blockchain Inc">
        <img class="blockchain-chip" v-if="cardInfo.vendor == 'blockchain'" src="@/assets/chip.svg" alt="chip">

        <img class="ninja-chip"  v-if="cardInfo.vendor == 'ninja'" src="@/assets/chip.svg" alt="chip">
        <img class="ninja-logo" v-if="cardInfo.vendor == 'ninja'" src="@/assets/ninja.svg" alt="Ninja Bank">

       
        
      </header>
   

         <p class="numbers">{{ cardInfo.cardNumber }}</p>
      <section class="card-input">
        <div class="name">
          <p class="cardInfo">Carholder name</p>
          <p class="cardHolder">{{cardInfo.cardHolder}}</p>
        </div>
        <div class="valid">
          <p class="cardInfo">valid thru</p>
          <p class="optionValid">{{cardInfo.expireYear}}</p>
        </div>
      </section>
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
        }else if (this.cardInfo.vendor == 'ninja'){
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

<style lang="scss">



.evil {
    background: linear-gradient(248.3deg, rgba(0, 0, 0, 0.16) 0%, rgba(0, 0, 0, 0) 100%), #F33355;
    color: white;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
    border-radius: 8px
}
.blockchain {
    background: linear-gradient(248.52deg, rgba(0, 0, 0, 0.15) 1.49%, rgba(0, 0, 0, 0) 100%), #8B58F9;
    color: white;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
    border-radius: 8px
}
.bitcoin {
    background: linear-gradient(248.04deg, rgba(255, 255, 255, 0.15) 0%, rgba(255, 255, 255, 0) 99.07%), #FFAE34;
    color: #222;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
    border-radius: 8px
}
.ninja {
    background: linear-gradient(248.3deg, rgba(255, 255, 255, 0.15) 0%, rgba(255, 255, 255, 0) 100%), #222222;
    color: white;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
    border-radius: 8px
}
.blank {
    background: linear-gradient(237.75deg, rgba(255, 255, 255, 0.24) 0%, rgba(255, 255, 255, 0) 100%), #D0D0D0;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
    border-radius: 8px
}


.card {
    width: 382px;
    height: 241px;
    position: relative;
    border-radius: 10px;
    font-family: "PT Mono";
    margin: 10px;

filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.12));
}
</style>