<template>
<Header />
<ProductDisplay :premium="premium" />
</template>

<script>
import ProductDisplay from './components/ProductDisplay.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    ProductDisplay,
    Header
  },
  data() {
    return {
      cart: 0,
      premium: true
    }
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
