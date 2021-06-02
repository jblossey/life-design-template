<template>
  <b-row>
    <b-col cols="1" class="my-auto">
      <div id="stageTitle">
        {{stageTitle}}
      </div>
    </b-col>
    <CustomCardsContainer :customCardTitle="Object.keys(stageData)[0]"
      :customCardData="stageData[Object.keys(stageData)[0]]"/>
    <StandardCardsContainer :standardCardTitle="Object.keys(stageData)[1]"
      :standardCardData="stageData[Object.keys(stageData)[1]]"/>
  </b-row>
</template>

<script>
import CustomCardsContainer from './CustomCardsContainer.vue';
import StandardCardsContainer from './StandardCardsContainer.vue';

export default {
  name: 'Stage',
  data() {
    return {
      customCardTitle: String,
      standardCardTitle: String,
      customCardData: Object,
      standardCardData: Object,
    };
  },
  props: {
    stageData: Object,
    stageTitle: String,
  },
  components: {
    CustomCardsContainer,
    StandardCardsContainer,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #stageTitle {
    transform: rotate(-90deg);
  }
</style>
