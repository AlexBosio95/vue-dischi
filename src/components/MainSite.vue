<template>
  <main>
    <div class="row">
      <div class="col-3">
        <MusicCard />
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

    }
  },
  methods:{
    getData(){
      axios.get('')
      .then((result) => {
          console.log(result)
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
}

</style>