<template>
  <main>
    <div class="container">

      <div v-if="!isLoad">
        <LoadingCard />
      </div>
      <div class="d-flex flex-wrap" v-if="isLoad">

            <SelectorSearch @search="getSelection" class="m-4"/>

            <AuthorSearch @search="getAuthor" class="m-4"/>

            <MusicCard v-for="(card, index) in filteredDisks" 
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
import LoadingCard from './LoadingCard.vue';
import SelectorSearch from './SelectorSearch.vue';
import AuthorSearch from './AuthorSearch.vue';


export default {

  components:{
    MusicCard,
    LoadingCard,
    SelectorSearch,
    AuthorSearch,
  },

  data: function(){
    return{
      MusicCards: [],
      isLoad: false,
      cardItem: [],
      filteredDisks: [],
      authorItem: [],
      filteredAuthor: [],

    }
  },
  methods:{
    getData(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((result) => {
          this.MusicCards = result.data.response;
          this.filteredDisks = this.MusicCards;
          setTimeout(() => {
              this.isLoad = true
          }, 1000); 
          
      })
      .catch((error) => {
          console.log(error)
      })
    },

    getSelection(item) {
      console.log(item)
      if(item == 'All Genres...') {
        this.filteredDisks = [...this.MusicCards]
      } else {
        this.filteredDisks = [...this.MusicCards].filter((cardItem) => cardItem.genre.includes(item))
      }
    },

    getAuthor(item) {
      console.log(item)
      if(item == 'All Author...') {
        this.filteredDisks = [...this.MusicCards]
      } else {
        this.filteredDisks = [...this.MusicCards].filter((authorItem) => authorItem.author.includes(item))
        console.log(this.filteredDisks)
      }
    }
    

  },

  // computed:{
  //     getSelection(item) {
  //     return [...this.MusicCards].filter((cardItem) => cardItem.genre.toLowerCase().includes(item))
  //   }
  // },

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