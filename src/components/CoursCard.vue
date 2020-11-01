<template>
<div>
    <div
    class="border m-4 p-4 flex justify-between"
    >
        <div>
            <h1 class="text-lg font-bold">{{ TitreCoursMajuscule }}</h1>
            <img :src="require('../assets/img/' + unCours.image)" />
            <h2 class="font-bold"> Durée : {{ unCours.duree }}</h2>
            <p class="font-bold"> Professeur : {{ unCours.professeur }}</p>
            <p class="font-bold"> Description : {{ unCours.description }}</p>
            <p class="font-bold"> Prix : {{ unCours.prix }}</p>
        </div>
        <base-button
            text="Ajouter au panier"
            @click="ajoutLesCours"
        >
        </base-button>
    </div>
</div>
</template>

<script>

export default {
    name: "unCours-card",
    props: ['unCours'],
    data(){
        return {
            lesCours: []
        }
    },
    computed: {
        TitreCoursMajuscule() {
            return this.unCours.nom.toUpperCase()
        }
    },
    methods: {
        ajoutLesCours() {
            this.$emit('ajout-uncours', this.unCours)
        }
    }
}
</script>

<style scoped>
    img {
        height: 100px;
    }

</style>
