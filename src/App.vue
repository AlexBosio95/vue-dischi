<template>
  <div id="app">
    <HeaderSite />
    <MainSite />
  </div>
</template>

<script>
import HeaderSite from './components/HeaderSite.vue';
import MainSite from './components/MainSite.vue';

export default {
  name: 'App',
  components: {
    HeaderSite,
    MainSite,
  }
}
</script>

<style lang="scss">

</style>
