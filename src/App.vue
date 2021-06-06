<template>
  <div class="w-100 h-100">
    <Navbar/>
    <GridContainer/>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import GridContainer from './components/GridContainer.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    GridContainer,
  },
};
</script>

<style lang="scss">
  @import "assets/custom.scss";
  @import "~bootstrap/scss/bootstrap.scss";
  @import '~bootstrap-vue/dist/bootstrap-vue.css';
</style>
