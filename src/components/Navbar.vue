<template>
  <div>
    <b-navbar toggleable="true" type="dark" variant="dark" class="p-2">
        <b-navbar-brand href="#">DYHL Card Template</b-navbar-brand>
        <b-button
          @click="$emit('exportToPdfTrigger')"
          variant="light"
          style="margin-left: auto; margin-right: 1em;"
        >
          Export to PDF
        </b-button>
        <b-button v-b-toggle.menu variant="light">Menu</b-button>
        <b-sidebar
          title="Jump To..."
          id="menu"
          shadow
          bg-variant="dark"
          text-variant="light"
          backdrop
          no-enforce-focus
          right
          no-header-close
        >
          <b-nav vertical class="w-50" v-for="(stage, key) in cardContents" :key="key">
            <b-nav-item :href="'#'+key">{{key}}</b-nav-item>
          </b-nav>
        </b-sidebar>
    </b-navbar>
    <!--
      <b-navbar toggleable="true" type="dark" variant="dark" class="p-2">
        <b-navbar-brand href="#">DYHL Card Template</b-navbar-brand>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav v-for="(stage, key) in cardContents" :key="key">
                <b-nav-item :href="'#'+key">{{key}}</b-nav-item>
            </b-navbar-nav>
        </b-collapse>
    </b-navbar>
    -->
  </div>
</template>

<script>
import cardData from '../assets/card-data.json';

export default {
  name: 'Navbar',
  data() {
    return { cardContents: cardData };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  a {
    text-decoration: none;
    color: inherit
  }
</style>
