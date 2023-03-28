<template lang="">
    <div class="button-container">
        <button class="start-button" @click="handleClick" :disabled="gameon">Test my reactions!</button>
    </div>
</template>

<script>
export default {
    name: "Startbutton",
    props: ['delay', 'gameon'],
    methods: {
        handleClick() {
            console.log('btn clicked!', this.gameon)
            this.$emit('start-timer')
        }
    }
}
</script>
<style scoped>
.button-container {
    height: 200px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.start-button {
    height: 50px;
    width: fit-content;
    transition: all 0.2s;
    padding: 1rem;
    font-size: medium;
    font-weight: bolder;
    border: 0.5rem darkgrey solid;
    background-color: rgb(77, 76, 76);
    border-radius: 20px;
    display: flex;
    align-items: center;
    cursor: pointer;
    color: white;
}

.start-button:hover {
    transform: scale(1.2);
}

.start-button:disabled {
    border: 0.2rem #a7a5a5 solid;
    background-color: #d6d1d1;
    color: rgb(164, 162, 162);
}

.start-button:disabled:hover {
    transform: none;
}
</style>