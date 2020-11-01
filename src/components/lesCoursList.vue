<template>
    <div class="container w-4/5 mx-auto mt-4">
        <h1 class="text-lg font-bold">Les cours :</h1>

        <div v-if="lesCours.length == 0">
            <p>Vous n'avez aucun cours</p>
        </div>
        <div v-else>
            <div
                    v-for="unCours in lesCours"
                    :key="unCours.nom"
                    class="border border-black my-4 p-2 flex flex-row"
            >
                <div class="flex flex-col space-x-4 m-auto">
                <h2 class="text-lg font-bold text-center">{{ unCours.nom }}</h2>
                <img class="mb-5" :src="require('../assets/img/' + unCours.image)" />
                </div>
                <div class="flex flex-col my-5 m-auto">
                <span class="font-bold">Professeur : </span>
                <p> {{ unCours.professeur }}</p>
                <span class="font-bold">Durée : </span>
                <p> {{ unCours.duree }}</p>
                <span class="font-bold">Description :</span>
                <p> {{ unCours.description }}</p>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'lesCours-list',
    props: ['lesCours'],

}
</script>

<style>

    img {
        max-height: 150px;
        max-width: 200px;
    }
</style>
