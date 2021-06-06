<template>
  <div class="w-100 h-100">
    <Navbar @exportToPdfTrigger="exportToPdf"/>
    <GridContainer ref="document"/>
  </div>
</template>

<script>
import html2pdf from 'html2pdf.js';
import Navbar from './components/Navbar.vue';
import GridContainer from './components/GridContainer.vue';

export default {
  name: 'App',
  methods: {
    exportToPdf: () => {
      html2pdf(document.querySelector('#gridcontainer'), {
        margin: 1,
        filename: 'my_life_design.pdf',
        image: { type: 'jpeg', quality: 0.98 },
        jsPDF: { unit: 'cm', format: 'a4', orientation: 'landscape' },
        pageBreak: { avoid: '.row' },
      });
    },
  },
  components: {
    Navbar,
    GridContainer,
  },
};
</script>

<style lang="scss">
  @import "assets/custom.scss";
  @import "~bootstrap/scss/bootstrap.scss";
  @import '~bootstrap-vue/dist/bootstrap-vue.css';

  .row {
    break-after: auto;
    break-inside: avoid;
  }
</style>
