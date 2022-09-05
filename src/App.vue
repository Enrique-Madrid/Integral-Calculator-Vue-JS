<template>
  <div class="crt"></div>
  <main-window></main-window>
</template>

<script>
import mainWindow from './components/mainWindow.vue'

export default {
  name: 'App',
  components: {
    mainWindow,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #010191;
}

.crt:after{
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    background: url('https://static.doomworld.com/monthly_2019_05/scanlines.png.2859237ac5e64816bb01978e0707b2db.png');
    background-repeat: repeat;
    background-size: auto 100%;
    background-position: center;
    opacity: 0.4;
}


</style>
