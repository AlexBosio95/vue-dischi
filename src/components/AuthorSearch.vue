<template>
  <div class="input-group">
        <select class="form-select" id="inputGroupSelect04" aria-label="Example select with button addon" v-model="searchAuthor">
            <option selected>All Author...</option>
            <option value="Bon Jovi">Bon Jovi</option>
            <option value="Queen">Queen</option>
            <option value="Sting">Sting</option>
            <option value="Steve Gadd Band">Steve Gadd Band</option>
            <option value="Iron Maiden">Iron Maiden</option>
            <option value="Eric Clapton">Eric Clapton</option>
            <option value="Deep Purple">Deep Purple</option>
            <option value="Metallica">Metallica</option>
            <option value="Dave Weckl">Dave Weckl</option>
            <option value="Michael Jacjson">Michael Jacjson</option>
        </select>
        <button class="btn btn-secondary" type="button" @click="$emit('search', searchAuthor)">Search Author</button>
    </div>
</template>

<script>
export default {
    data: function() {
        return{
            searchAuthor: 'All Author...',
        }
    },
    created(){
        
        
    }

}
</script>

<style>

</style>