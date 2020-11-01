<template>
    <div class="bg-blue-400 text-center p-5 ">
        <a class="pr-2 font-bold white" href="#" @click="changeComponent('cours-view')">Tous les cours</a> |
        <a class="pl-2 font-bold" href="#" @click="changeComponent('lesCours-list')">Les cours</a>
    </div>
</template>

<script>
export default {
    name: "navigation-bar",
    methods : {
        changeComponent(value) {
            this.$emit('change-component', value)
        }
    }
}
</script>

<style scoped>

a {
    color: white;
}

</style>
