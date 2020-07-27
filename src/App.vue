<template>
  <div id="app">
    <!--img alt="Vue logo" src="./assets/logo.png"-->
    <div id="content">
      <ImagePlaceholder title_msg="Podgląd koszulki" v-bind:class="side" v-on:set-placement="setPlacement($event)"/>
      <div id="order-steps">
        <component v-bind:is="selected"></component>
        <div class="pager">
          <span
                v-for="formStep in formSteps"
                :key="formStep"
                @click="selected = formStep;"
                :class="[{ active: selected === formStep }]"
        >
          {{ formStep }}
        </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ImagePlaceholder from './components/ImagePlaceholder.vue'
import ChoosePlacement from './components/steps/ChoosePlacement.vue'
import ChoosePhoto from './components/steps/ChoosePhoto.vue'
import ChooseStyle from './components/steps/ChooseStyle.vue'
import DesignSummary from './components/steps/DesignSummary.vue'
import BuyerDetails from './components/steps/BuyerDetails.vue'
import DeliveryDetails from './components/steps/DeliveryDetails.vue'
import OrderSummary from './components/steps/OrderSummary.vue'
import ThankYouPage from './components/steps/ThankYouPage.vue'

export default {
  name: 'App',
  components: {
    ImagePlaceholder,
    ChoosePlacement,
    ChoosePhoto,
    ChooseStyle,
    DesignSummary,
    BuyerDetails,
    DeliveryDetails,
    OrderSummary,
    ThankYouPage
  },
  data: function () {
    return {
      formSteps: ["ChoosePlacement", "ChoosePhoto", "ChooseStyle", "DesignSummary", "BuyerDetails", "DeliveryDetails", "OrderSummary", "ThankYouPage"],
      selected: "ChoosePlacement",
      side: 'front'
    }
  },
  methods: {
    setPlacement(side){
      this.side = side
    },
    test(){
      return 'ok'
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: #fafafa;
}
  #content{
    display: grid;
    Width: 90%;
    height: 70%;
    max-width: 1000px;
    max-height: 700px;
    position: absolute;
    margin: 0 auto;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    padding: 2rem;
    background: #fff;
    box-shadow: 0 0 15px rgba(0,0,0,.5);
    grid-template-columns: 1fr 1fr;
  }
  #content h1{
    margin-top: 0;
    font-size: 1.5rem;
  }
  .product-wrapper{
    height: 100%;
    margin: 1rem;
    position:  relative;
    max-height: calc(100% - 4.5rem);
  }
  .product-wrapper:after{
    content: '';
    display: block;
    position: absolute;
    right: -2rem;
    height: 80%;
    top: 50%;
    transform: translateY(-50%);
    width: 2px;
    background: #ddd;
  }
  .product-wrapper>div{
    width: 100%;
    height: 100%;
  }
  .pager{
    position: absolute;
    bottom: 1rem;
    left: 50%;
    transform: translateX(-50%);
    z-index: 5;
  }
  .pager>span{
    text-indent: -5000px;
    text-align: left;
    background: #ddd;
    width: 1rem;
    height: 1rem;
    border-radius: 50%;
    display: inline-block;
    margin: 0 1rem;
    cursor: pointer;
  }
  .pager>span.active{
    background: #c00;
  }
  .container{
    margin: 4rem auto 0 auto;
    display: block;
    position: relative;
  }
  .container>span{
    font-size: 2rem;
    margin: 0 2rem;
    cursor: pointer;
  }
</style>
