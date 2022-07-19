<template>
  <div class="card">
      <h1>{{card.author}}</h1>
  </div>
</template>

<script>
export default {
    props: {
        card: Object,
        }

}
</script>

<style lang="scss" scoped>

@import "../styles/variabiles.scss";
div.card{
    background-color: $colorHeader;

    h1{
    color: $colorText;
    }

}


</style>