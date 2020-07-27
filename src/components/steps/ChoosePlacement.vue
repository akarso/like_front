<template>
  <div class="choose-placement">
    <h1>{{ title_msg }}</h1>
    <span class="container">
    <span v-on:click="setPlacement('front')">Przód</span> <span v-on:click="setPlacement('back')">Tył</span>
  </span>
  </div>
</template>

<script>
export default {
  name: 'ChoosePlacement',
  data: function(){
    return{
      title_msg: 'Wybierz stronę'
    }
  },
  methods: {
    setPlacement(side){
      this.$emit('set-placement', side)
    }
  }
}
</script>

<style scoped>

</style>
