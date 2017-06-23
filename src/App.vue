<template>
  <div id="app" class="container">
    <mainmenu v-on:activechange="changeComponent"></mainmenu> 
    <div id="main">
      <component v-bind:is="currentView">
      </component>
    </div>
  </div>
</template>

<script>
import mainmenu from './components/Menu/Menu.vue'
import home from './components/Pages/Home.vue'

export default {
  name: 'app',
  components: {home, mainmenu},
  data () {
    return {
      currentView: home
    }
  },
  methods: {
    changeComponent: function (item) {
      // Set the current view to the component related to the selected menu item
      this.currentView = item.component
    }
  }
}
</script>

<style>
body { 
  padding-top: 70px; 
}
</style>
