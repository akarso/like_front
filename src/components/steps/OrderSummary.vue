<template>
  <div class="order-summary">
    <h1>{{ title_msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'OrderSummary',
  data: function(){
    return{
      title_msg: 'Podsumowanie zamówienia'
    }
  }
}
</script>

<style scoped>

</style>
