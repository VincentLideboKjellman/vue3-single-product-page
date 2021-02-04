<template>
  <Socks/>
  <div class="background-div">
  <div class="viedo-div">
    <video controls width="500">
      <source src="battery.webm"
              type="video/webm">
      <!-- <source src=".mp4"
              type="video/mp4"> -->
    </video>
  </div>
  </div>
</template>

<script>
import Socks from './components/Socks.vue'

export default {
  name: 'App',
  components: {
    Socks
  }
}
</script>

<style>
.video-div{
  position: absolute;
  top: 20%;
}
.background-div{
  width:100%;
  height:100vh;
  position:relative;
  background-color: green;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
