<template>
  <button class="btn-blue">
    {{ text }}
  </button>
</template>

<script>
export default {
    props: ['text']
}
</script>

<style scoped>
.btn-blue {
  @apply bg-blue-400 text-white font-bold py-2 px-4 rounded;
}
.btn-blue:hover {
  @apply bg-blue-600;
}
</style>
