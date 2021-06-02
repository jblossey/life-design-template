<template>
  <b-col>
    <h3 class="text-center">
      {{cardTitle}}
    </h3>
    <div v-for="description in cardData" :key="description" class="description">
      {{description}}
    </div>
  </b-col>
</template>

<script>
export default {
  name: 'Card',
  props: {
    cardTitle: String,
    cardData: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .description {
    font-size: 0.5em;
  }
</style>
