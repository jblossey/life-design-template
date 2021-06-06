<template>
    <b-card
      :title="cardTitle"
      :sub-title="cardData[0]"
      :class="'text-center p-0 m-0 mb-2 ' + currentStage + 'Card'"
      border-variant="white"
      sub-title-text-variant=""
      :id="currentStage + stripAndDecapitalize(cardTitle) + 'Card'"
    >
      <b-card-body>
        <b-form-textarea
          :id="currentStage + stripAndDecapitalize(cardTitle) + 'Textarea'"
          class="m-0 p-0 pt-4"
          v-model="userInput"
          :placeholder="cardData[1]"
          rows="20"
          size="sm"
          no-resize
          :state="userInput.length < 244"
        />
      </b-card-body>
    </b-card>
</template>

<script>
export default {
  name: 'Card',
  props: {
    cardTitle: String,
    cardData: Array,
    stage: String,
  },
  data() {
    return {
      userInput: '',
      currentStage: this.stage,
    };
  },
  methods: {
    stripAndDecapitalize: (rawString) => rawString.toLowerCase().replace(/\s/g, ''),
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

  @import "../assets/custom.scss";
  @import "../../node_modules/bootstrap";

  .card-body {
    padding: 0px;
    padding-left: 1px;
    padding-right: 1px;
    color: inherit;
  }

  .card-title {
    @extend .rounded;
    word-wrap: normal;
    height: 3.5em;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .card-subtitle {
    word-break: keep-all;
    word-wrap: normal;
    height: 3.5em;
    color: inherit
  }

  .card {
    color:inherit;
  }

  .EmpathiseCard .card-title {
    background-color: map-get($map: $stage-colors, $key: "Empathise");
    color: white
  }

  .DefineCard .card-title {
    background-color: map-get($map: $stage-colors, $key: "Define");
    color: white
  }

  .IdeateCard .card-title {
    background-color: map-get($map: $stage-colors, $key: "Ideate");
    color: white
  }

  .PrototypeCard .card-title {
    background-color: map-get($map: $stage-colors, $key: "Prototype");
    color: white
  }

  .TestCard .card-title {
    background-color: map-get($map: $stage-colors, $key: "Test");
    color: white
  }
</style>
