<template>
  <div>

    <article class="card" v-bind:class="vendorSelect" @click="setCurrentCard">
       <header>
         
       <img 
       class="vendor-class"
       :src="vendorSrc"
       v-if="cardInfo.vendor"
        />
        <div class="chip-wifi">
        <img  src="@/assets/wifi_white.svg" alt="wifi">
        <img class="chip" src="@/assets/chip.svg" alt="chip">
        </div>
      </header>
   

         <p class="numbers">{{ cardInfo.cardNumber }}</p>
      <section class="card-input">
        <div class="name-valid">
          <section class="name">
          <p>Carholder name</p>
          <p class="card-holder">{{cardInfo.cardHolder}}</p>
        </section>
        <section class="valid">
          <p>Valid Thru</p>
          <p>{{cardInfo.expireYear}} / {{cardInfo.expireMonth}}</p>
          </section>
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

    },
    vendorSrc(){
      return require(`../assets/${this.cardInfo.vendor}.svg`)
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
    border-radius: 10px;
    font-family: "PT Mono";
    margin: 10px;

filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.12));
}
.numbers{
   
    display: flex;
    font-size: 1.6rem;
    letter-spacing: .05rem;
    padding: .5rem 0 0 0;
    margin-left: 110px;
   
}
.card header {
    display: flex;
    align-items: flex-start;
    flex-direction: row-reverse;
}
.card header img {
    opacity: .9;
}
.chip-wifi {
    
    margin-right: 240px;
    opacity: 1;
   
}
.name-valid{
  
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  transform: translateY(-16px);
  
  
  
    
    
}
.vendor-class{
  display: flex;
}
.chip{
  color: gold;
  background-color: rgb(184, 178, 144);
  border-radius: 7px;
}

</style>