<template>
  <b-col cols="3">
    <h2 class="text-center">
      {{customCardTitle}}
    </h2>
    <b-row>
      <Card v-for="(card, key) in customCardData"
        :key="key" :cardTitle="key" :cardData="card"/>
    </b-row>
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
    };
  },
  props: {
    customCardTitle: String,
    customCardData: Object,
  },
  components: {
    Card,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
