<template>
  <div class="ms_card">
      <img :src="card.poster" alt="">
      <h5 class="fw-bold">{{card.title}}</h5>
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

    h5{
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
        height: calc(100vw / 6 - 30px);
        object-fit: cover;
        
    }

}


</style>