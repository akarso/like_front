<template>
  <div class="image-placeholder">
    <h1 v-bind:class="test">{{ title_msg }}</h1>
    <div class="product-wrapper">
      <div class="stencil"></div>
      <div class="photo" :style="{ backgroundImage: 'url(\'' + loremPicsum + '\')' }"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ImagePlaceholder',
  props: {
    title_msg: String
  },
  data: function(){
    return {
      loremPicsum: 'https://picsum.photos/200?img=1'
    }
  },
  methods: {
    test: function(){
      return 'test'
    }
  }
}
</script>

<style scoped>
  .stencil{
    position: absolute;
    z-index: 1;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;
  }
  .front .stencil{
    background-image: url(./../assets/stencil-front.png);
  }
  .back .stencil{
    background-image: url(./../assets/stencil-back.png);
  }
  .photo{
    position: absolute;
    z-index: 2;
    max-width: 45%;
    max-height: 45%;
    left: 50%;
    transform: translateX(-50%);
    top: 25%;
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
  }
</style>
