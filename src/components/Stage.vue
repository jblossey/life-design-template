<template>
  <b-row :id="stageTitle">
    <b-col cols="1" class="my-auto stageTitleWrapper">
      <div class="stageTitle m-0 p-0">
        {{stageTitle}}
      </div>
    </b-col>
    <CustomCardsContainer
      :customContainerTitle="Object.keys(stageData)[0]"
      :customCardsData="stageData[Object.keys(stageData)[0]]"
      :id="'custom'+stageTitle"
      class="cardContainer m-1"
      :stage="stageTitle"
    />
    <StandardCardsContainer
      :standardContainerTitle="Object.keys(stageData)[1]"
      :standardCardsData="stageData[Object.keys(stageData)[1]]"
      :id="'custom'+stageTitle"
      class="cardContainer m-1"
      :stage="stageTitle"
    />
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
<style lang="scss" scoped>

  @import "../assets/custom.scss";

  .stageTitleWrapper {
    width: 5%;
  }

  .stageTitle {
    transform: rotate(-90deg);
  }

  .cardContainer {
    border-style:solid;
    border-radius: 1em;
  }

  /* stage-specific stylings */

  #customEmpathise {
    border-color: map-get($map: $stage-colors, $key: "Empathise");
    color: map-get($map: $stage-colors, $key: "Empathise");
  }
  #standardEmpathise {
    border-color: map-get($map: $stage-colors, $key: "Empathise");
    color: map-get($map: $stage-colors, $key: "Empathise");
  }

  #customDefine {
    border-color: map-get($map: $stage-colors, $key: "Define");
    color: map-get($map: $stage-colors, $key: "Define");
  }
  #standardDefine {
    border-color: map-get($map: $stage-colors, $key: "Define");
    color: map-get($map: $stage-colors, $key: "Define");
  }

  #customIdeate {
    border-color: map-get($map: $stage-colors, $key: "Ideate");
    color: map-get($map: $stage-colors, $key: "Ideate");
  }
  #standardIdeate {
    border-color: map-get($map: $stage-colors, $key: "Ideate");
    color: map-get($map: $stage-colors, $key: "Ideate");
  }

  #customPrototype {
    border-color: map-get($map: $stage-colors, $key: "Prototype");
    color: map-get($map: $stage-colors, $key: "Prototype");
  }
  #standardPrototype {
    border-color: map-get($map: $stage-colors, $key: "Prototype");
    color: map-get($map: $stage-colors, $key: "Prototype");
  }

  #customTest {
    border-color: map-get($map: $stage-colors, $key: "Test");
    color: map-get($map: $stage-colors, $key: "Test");
  }
  #standardTest {
    border-color: map-get($map: $stage-colors, $key: "Test");
    color: map-get($map: $stage-colors, $key: "Test");
  }
</style>
