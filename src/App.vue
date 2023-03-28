
<template>
  <h1>This will be an reation timer APP!</h1>
  <Startbutton />
  <Popupbox />
</template>

<script>
import Popupbox from './components/Popupbox.vue';
import Startbutton from './components/Startbutton.vue';

export default {
  name: "App",
  components: { Popupbox, Startbutton }
}
</script>

<style scoped></style>
