<template>
  <div class="input-group">
        <select class="form-select" id="inputGroupSelect04" aria-label="Example select with button addon" v-model="selGenre">
            <option selected>All Genres...</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
        <button class="btn btn-secondary" type="button" v-on="$emit('search', selGenre)">Search</button>
    </div>
    

</template>

<script>
export default {
    data: function() {
        return{
            selGenre: '',
        }
    },
    created(){
        
        
    }

}
</script>

<style lang="scss" scoped>

@import "../styles/variabiles.scss";


</style>