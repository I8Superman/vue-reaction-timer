<template>
    <div class="results">
        Your reaction time was: {{ result }}
    </div>
</template>

<script>
export default {
    name: 'Results',
    props: ['result']
}
</script>

<style scoped>
.results {
    font-size: 3rem;
}
</style>