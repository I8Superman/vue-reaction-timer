<template>
    <div class="popup" v-if="showPopup" @click="stopReactionTimer">
        Click me fast you sonofabitch!!!
    </div>
</template>

<script>
export default {
    name: 'Popupbox',
    props: ['delay'],
    data() {
        return {
            showPopup: false,
            popupClicked: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showPopup = true
            console.log(this.delay)
            this.startReactionTimer()
        }, this.delay)
    },
    // updated() {
    //     console.log(this.reactionTime)
    // },
    methods: {
        startReactionTimer() {
            console.log('Reaction timer started!')
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopReactionTimer() {
            clearInterval(this.timer)
            console.log(this.reactionTime)
        }
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