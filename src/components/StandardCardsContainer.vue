<template>
  <b-col cols="8">
    <h2 class="text-center containerTitle mx-auto my-0 text-nowrap">
      {{standardContainerTitle}}
    </h2>
    <b-card-group>
      <Card
        v-for="(card, key) in standardCardsData" :key="key"
        :cardTitle="key"
        :cardData="card"
        :stage="currentStage"
      />
    </b-card-group>
  </b-col>
</template>

<script>
import Card from './Card.vue';

export default {
  name: 'StandardCardsContainer',
  data() {
    return {
      cardTitle: String,
      cardData: Array,
      currentStage: this.stage,
    };
  },
  props: {
    standardContainerTitle: String,
    standardCardsData: Object,
    stage: String,
  },
  components: {
    Card,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .containerTitle {
    transform: translateY(-1rem);
    background-color: white;
    width:50%;
  }
</style>
