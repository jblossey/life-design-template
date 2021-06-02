<template>
  <b-col cols="8">
    <h2 class="text-center">
      {{standardCardTitle}}
    </h2>
    <b-card-group>
      <Card v-for="(card, key) in standardCardData"
        :key="key" :cardTitle="key" :cardData="card"/>
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
    };
  },
  props: {
    standardCardTitle: String,
    standardCardData: Object,
  },
  components: {
    Card,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
