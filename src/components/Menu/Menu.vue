
<template>
  <nav class="navbar navbar-default navbar-fixed-top">
    <div class="container-fluid">
      <div class="navbar-header">
        <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar-collapse" aria-expanded="false">
          <span class="sr-only">Toggle navigation</span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>
        <img src="./../../assets/logo.png" class="navbar-brand">
      </div>

      <div class="collapse navbar-collapse" id="navbar-collapse">
        <ul class="nav navbar-nav">
          <li v-for="i in items" v-bind:class="{active: i.name==active.name}"><a href="#" v-on:click="makeActive(i)">{{ i.name }}<span class="sr-only">(current)</span></a></li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
import home from './../Pages/Home.vue'
import colouring from './../Pages/Colouring.vue'

export default {
  name: 'menu',
  components: {home, colouring},
  data () {
    return {
      items: [
        { 'name': 'Home', 'component': home },
        { 'name': 'Colouring', 'component': colouring }
      ],
      active: { 'name': 'Home', 'component': home }
    }
  },

  methods: {
    makeActive: function (activeItem) {
      this.active = activeItem
      // Pass selection through to the activechange function
      // on the root vue class
      this.$emit('activechange', this.active)
    }
  }
}
</script>

<style scoped>

nav {
  border-top: 1px solid #ef2f86;
  border-bottom: 1px solid #ef2f86;
}

a {
  color: #ef2f86 !important;
  font-family: "Palatino Linotype";
  font-size: 120%;
}

a:hover {
  background-color: #e7e7e7 !important;
}

.active a {
  background-color: #ef2f86 !important;
  color: #e7e7e7 !important;
}
img {
  background-color: #ef2f86 !important;
}

</style>
