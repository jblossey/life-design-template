<template>
  <b-col cols="3">
    <h2
      class="text-center containerTitle mx-auto my-0 text-nowrap"
      :id="customContainerTitle.toLowerCase().replace(/\s/g, '') + 'Title'"
    >
      {{customContainerTitle}}
    </h2>
    <b-card-group>
      <Card
        v-for="(card, key) in customCardsData" :key="key"
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
  name: 'CustomCardsContainer',
  data() {
    return {
      cardTitle: String,
      cardData: Array,
      currentStage: this.stage,
    };
  },
  props: {
    customContainerTitle: String,
    customCardsData: Object,
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
    width:75%;
  }
</style>
