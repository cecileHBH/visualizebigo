<template>
  <div id="app">
    <div class="main-panel">
      <Menu/>
      <Concept msg="Welcome to Visualize Big-O"/>
      <Sorting/>
      <Contact/>
    </div>
  </div>
</template>

<script>
import Menu from './components/Menu.vue'
import Concept from './components/Concept.vue'
import Sorting from './components/Sorting.vue'
import Contact from './components/Contact.vue'

import Vue from 'vue'

import VueGraph from 'vue-graph'
import GraphLine3D from 'vue-graph/src/components/line3d.js'
import NoteWidget from 'vue-graph/src/widgets/note.js'
import LegendWidget from 'vue-graph/src/widgets/legends.js'

import BootstrapVue from 'bootstrap-vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

Vue.use(VueGraph);
Vue.component(GraphLine3D.name, GraphLine3D);
Vue.component(NoteWidget.name, NoteWidget);
Vue.component(LegendWidget.name, LegendWidget);

Vue.use(BootstrapVue);
export default {
  name: 'app',
  components: {
    Menu,
    Concept,
    Sorting,
    Contact
  }
}
</script>

<style>
#app {
  background-color: #083248;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /*margin-top: 60px;*/
}
.main-panel {
  float: left;
  width: 100%;
  height: 100vh;
}
</style>
