<template>
  <div class="buyer-details">
    <h1>{{ title_msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'BuyerDetails',
  data: function(){
    return{
      title_msg: 'Dane zamówienia'
    }
  }
}
</script>

<style scoped>

</style>
