<script>
import MainHeader from './components/MainHeader.vue';
import MainMain from './components/MainMain.vue';
import MainFooter from './components/MainFooter.vue';

export default {
    name: "",
    components: {
      MainHeader,
      MainMain,
      MainFooter
    }
}
</script>

<template>
  <MainHeader/>
  <MainMain/>
  <MainFooter/>
</template>

<style lang="scss">
  @use "./style/partials/general.scss";
  @use "./style/partials/_variables.scss";
</style>
