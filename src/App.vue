<template>
<Header />
<Socks />
</template>

<script>
import Socks from './components/Socks.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Socks,
    Header
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
