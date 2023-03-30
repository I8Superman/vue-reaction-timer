<template>
    <div class="results">
        Your reaction time was: {{ result }} <br>
        <h3>{{ rank }}</h3>
    </div>
</template>

<script>
export default {
    name: 'Results',
    props: ['result'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if (this.result < 350) {
            this.rank = 'Speedy Gonzales jajaja!'
        } else if (this.result < 450) {
            this.rank = "You're pretty, pretty, prettiii fast...!"
        } else if (this.result < 650) {
            this.rank = "Could be faster..."
        } else {
            this.rank = "Jebus you're slow dude!"
        }
        console.log(this.rank)
    }
}

</script>

<style scoped>
.results {
    font-size: 3rem;
}

h3 {
    font-weight: bolder;
    color: brown;
}
</style>