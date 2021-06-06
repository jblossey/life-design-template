<template>
  <b-container fluid class="mx-auto p-0 w-100" id="gridcontainer">
      <Stage
        v-for="(stage, key) in cardContents" :key="key"
        v-bind:stageData="stage"
        :stageTitle="key"
        class="m-2 p-1 flex-nowrap"
      />
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
</style>
