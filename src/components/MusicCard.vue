<template>
  <div class="ms_card">
      <img :src="card.poster" alt="">
      <h4 class="fw-bold">{{card.title}}</h4>
      <h6>{{card.author}}</h6>
      <h6>{{card.year}}</h6>
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

div.ms_card{
    background-color: $colorHeader;
    padding: 1rem;
    margin: 20px 15px;

    h4{
    color: $colorText;
    text-transform: uppercase;
    text-align: center;
    margin-top: 0.5rem;
    }

    h6{
    color: $colorTextAuthor;
    text-align: center;
    margin-top: 0.5rem;
    }

    img{
        width: 100%;
        object-fit: cover;
        
    }

}


</style>