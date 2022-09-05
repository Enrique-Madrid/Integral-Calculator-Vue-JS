<template>
  <background-anim class="background h-screen blur-xs"></background-anim>
  <alert-frame class="alert blur-xs"></alert-frame>
  <main-text class="blur-xs"></main-text>
  <calc-frame class="blur-xs"></calc-frame>
</template>

<script>
import mainText from './mainText.vue';
import backgroundAnim from './backgroundAnim.vue'
import calcFrame from './calcFrame.vue';
import alertFrame from './alert.vue';

export default {
    name: "mainWindow",
    components: {
    mainText,
    backgroundAnim,
    calcFrame,
    alertFrame,
},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.alert{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;
}

.background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}
</style>
