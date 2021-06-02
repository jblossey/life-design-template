<template>
    <b-card
      :title="cardTitle"
      bg-variant="dark"
      text-variant="light"
      class="text-center"
      border-variant="light"
      body-bg-variant="light"
      body-border-variant="dark"
    >
      <b-card-text v-for="description in cardData" :key="description">
        {{description}}
      </b-card-text>
    </b-card>
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
