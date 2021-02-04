<template>
<Header />
<Socks />
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
body {
  background-color: #f2f2f2;
  margin: 0px;
  font-family: tahoma;
  color: #282828;
}
</style>
