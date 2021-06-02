<template>
  <div>
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

  h2 {
    font-size: 1.5em;
  }

  h3 {
    font-size: 1.25em;
  }
</style>
