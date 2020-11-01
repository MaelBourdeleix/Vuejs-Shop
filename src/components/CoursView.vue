<template>
    <div class="flex justify-center">
    <mon-panier
      :lesCours="lesCours"
      @change-component="changeSelectedComponent"
    >
    </mon-panier>

    <div>
    <unCours-card
    v-for="(unCours, index) in cours.cours"
    :key="index"
    :unCours="unCours"
    @ajout-uncours="ajoutCoursPanier"
    >
    </unCours-card>
    </div>
  </div>
</template>

<script>
import coursData from '../data/cours.json'
import unCoursCard from '../components/CoursCard.vue'
import MonPanier from '../components/MonPanier.vue'


export default {
    name: 'unCours-view',
  components: {
    unCoursCard,
    MonPanier

  },
  data() {
        return {
            cours: coursData,
            lesCours: []
        }
    },
    methods: {
      ajoutCoursPanier(unCours) {
        this.lesCours.push(unCours)
        this.$emit('child-event', unCours)
      },
    }
}

</script>

<style>

</style>
