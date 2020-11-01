<template>
  <div>

    <navigation-bar
    @change-component="changeSelectedComponent">

    </navigation-bar>

  <keep-alive include="player-view">
        <component
          :is="selectedComponent"
          v-bind="currentProps"
          @child-event="lesCoursPush"
          >

          </component>
  </keep-alive>
    </div>
</template>

<script>

import CoursView from './components/CoursView.vue'
import lesCoursList from './components/lesCoursList.vue'
import NavigationBar from './components/navigation/NavigationBar.vue'

export default {
  name: 'App',
  components: {
    CoursView,
    lesCoursList,
    NavigationBar
  },
  data() {
    return {
      selectedComponent: 'cours-view',
      coursPanier:[]
    }
  },
  computed: {
    currentProps() {
      if(this.selectedComponent == "lesCours-list") {
      return { lesCours: this.coursPanier }
      }
      return false
    }
  },
  methods: {
    changeSelectedComponent(value) {
      this.selectedComponent = value
    },
    lesCoursPush(value){
      this.coursPanier.push(value)
    }
  }
}
</script>

<style>


</style>
