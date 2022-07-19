<template>
  <main>
    <div class="container">
    <div class="d-flex flex-wrap">
          <MusicCard v-for="(card, index) in MusicCards" 
          :key="index" 
          :card="card"
          class="card"
          />
      </div>
    </div>

  </main>
</template>

<script>
import axios from 'axios';
import MusicCard from './MusicCard.vue';

export default {

  components:{
    MusicCard,
  },

  data: function(){
    return{
      MusicCards: []

    }
  },
  methods:{
    getData(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((result) => {
          console.log(result.data.response)
          this.MusicCards = result.data.response
          console.log(this.MusicCards)
      })
      .catch((error) => {
          console.log(error)
      })
    }

  },

  created(){
    this.getData()
  }

}
</script>

<style lang="scss" scoped>

@import "../styles/variabiles.scss";


main{
  height: 93vh;
  background-color: $colorBg;

  .card{
    width: calc(100% / 5);
  }
}

</style>