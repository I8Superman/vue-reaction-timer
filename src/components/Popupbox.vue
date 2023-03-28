<template>
    <div class="popup">
        Click me fast you sonofabitch!!!
    </div>
</template>

<script>
export default {
    name: 'Popupbox',
    props: ['delay'],
    mounted() {
        setTimeout(() => {
            console.log(`Time's up! Timer was set at ${this.delay}`)
        }, this.delay)
    }
}
</script>

<style scoped>
.popup {
    width: 500px;
    height: 300px;
    border-radius: 20px;
    text-align: center;
    border: 0.5rem solid green;
    background-color: greenyellow;
    padding: 3rem;
    color: darkgreen;
    font-size: 3rem;
    font-weight: bolder;
    cursor: pointer;
}
</style>