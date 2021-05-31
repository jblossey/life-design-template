<template>
  <div>
      <b-navbar toggleable="true" type="dark" variant="dark" class="p-2">
        <b-navbar-brand href="#">DYHL Card Template</b-navbar-brand>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav>
                <b-nav-item href="#">Empathise</b-nav-item>
                <b-nav-item href="#">Define</b-nav-item>
                <b-nav-item href="#">Ideate</b-nav-item>
                <b-nav-item href="#">Prototype</b-nav-item>
                <b-nav-item href="#">Test</b-nav-item>
            </b-navbar-nav>
        </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
