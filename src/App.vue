<template>
  <div class="w-100 h-100">
    <Navbar
      @exportToPdfTrigger="exportToPdf"
      @saveToCookieTrigger="saveInputToCookie"
      @loadFromCookieTrigger="loadInputFromCookie"
    />
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
    saveInputToCookie() {
      const textareas = document.getElementsByTagName('textarea');
      const textareasCookie = {};
      [...textareas].forEach((area) => {
        textareasCookie[area.id] = area.value;
      });
      const obfuscatedContentsAsJson = btoa(JSON.stringify(textareasCookie));
      this.$cookies.set('life_design_template_save', obfuscatedContentsAsJson);
      // eslint-disable-next-line no-alert
      alert('Your Input has been saved to a cookie in your browser.\nThe cookie will be valid for 30 days or until you delete your cookies.');
    },
    loadInputFromCookie() {
      const obfuscatedCookie = this.$cookies.get('life_design_template_save');
      const textareaContents = JSON.parse(atob(obfuscatedCookie));
      const textareas = document.getElementsByTagName('textarea');
      [...textareas].forEach((area) => {
        // eslint-disable-next-line no-param-reassign
        area.value = textareaContents[area.id];
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
