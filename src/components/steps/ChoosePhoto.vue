<template>
  <div class="choose-photo">
    <h1>{{ title_msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'ChoosePhoto',
  data: function(){
    return{
      title_msg: 'Wybierz zdjęcie'
    }
  }
}
</script>

<style scoped>

</style>
