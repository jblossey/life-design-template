<template>
  <b-container class="mx-auto" id="gridcontainer">
      <Stage v-for="(stage, key) in cardContents" :key="key"
        v-bind:stageData="stage" :stageTitle="key"/>
  </b-container>
</template>

<script>
import Stage from './Stage.vue';
import cardData from '../assets/card-data.json';

export default {
  name: 'GridContainer',
  data() {
    return { cardContents: cardData };
  },
  components: {
    Stage,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #gridcontainer {
    width: 100%;
  }
</style>
