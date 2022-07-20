<template>
  <div class="row mt-4">

    <div class="col-4"></div>
    
    <div class="col-4">
        <h1>Loading...</h1>
        <div class="progress">
            <div class="progress-bar progress-bar-striped progress-bar-animated" role="progressbar" aria-label="Animated striped example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100" style="width: 75%"></div>
        </div>
    </div>
    
    <div class="col-4"></div>

    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import "../styles/variabiles.scss";

h1{
    color: $colorText;
}

</style>