<template>
    <div>
        <div class="border border-black text-center m-4 p-4">
            <h2 class="text-lg font-bold">Votre panier</h2>
            <br>
            Nombre de cours au panier : {{ lesCours.length }}
            <span>cours</span>
            <h2 class="text-lg font-bold">Liste des cours :</h2>

            {{ nomCours }}

            <ul>
                <li v-for="unCours in lesCours"
                    :key="unCours.nom"
                >
                    {{unCours.nom}} prix: - {{unCours.prix}}
                </li>
            </ul>

            <br>

            <p>
                Total du panier =
            </p>

        </div>
    </div>
</template>

<script>
export default {
    name: "mon-panier",
    props: ['lesCours'],
    computed: {
        numberSelection() {
            if(this.selection < 2) {
                return true
            }
            return false
        },
    }
}
</script>

<style>

</style>
