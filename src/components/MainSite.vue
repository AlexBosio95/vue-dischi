<template>
  <main>
    <div class="container">

      <div v-if="!isLoad">
        <LoadingCard />
      </div>
      <div class="d-flex flex-wrap" v-if="isLoad">
            <SelectorSearch class="m-4"/>

            <MusicCard v-for="(card, index) in MusicCards" 
            :key="index" 
            :card="card"
            class="ms_card"/>
        </div>
    </div>

  </main>
</template>

<script>
import axios from 'axios';
import MusicCard from './MusicCard.vue';
import LoadingCard from './LoadingCard.vue'
import SelectorSearch from './SelectorSearch.vue'

export default {

  components:{
    MusicCard,
    LoadingCard,
    SelectorSearch,
  },

  data: function(){
    return{
      MusicCards: [],
      isLoad: false

    }
  },
  methods:{
    getData(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((result) => {
          this.MusicCards = result.data.response
          setTimeout(() => {
              this.isLoad = true
          }, 1000); 
          
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
  overflow-y: scroll;

  .ms_card{
    width: calc(100% / 5 - 30px);
  }
}

</style>