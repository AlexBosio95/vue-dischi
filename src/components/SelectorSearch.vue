<template>
  <div class="input-group">
        <select class="form-select" id="inputGroupSelect04" aria-label="Example select with button addon">
            <option selected>All Genres...</option>
            <option value="1">Rock</option>
            <option value="2">Pop</option>
            <option value="3">Jazz</option>
            <option value="4">Metal</option>
        </select>
        <button class="btn btn-secondary" type="button">Button</button>
</div>
</template>

<script>
export default {

    props: {
        card: Object,
    },
    data: function() {
        return{
            genArray: [],
        }
    },

}
</script>

<style lang="scss" scoped>

@import "../styles/variabiles.scss";



</style>