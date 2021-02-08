<template>
<Header />
<div class="cart">Cart({{ cart.length }})</div>
<ProductDisplay :premium="premium" @add-to-cart="updateCart" @remove-from-cart="removeFromCart" />
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
      cart: [],
      premium: true
    }
  },
  methods: {
    updateCart(id){
      this.cart.push(id)
    },
    removeFromCart(id){
      this.cart.splice(0, 1)
      
      // this.list.map(x => {
      //   return x.id;
      // }).indexOf(id);

      // list.splice(index, 1);
    }
  },
}
</script>

<style>
body {
  background-color: #f2f2f2;
  margin: 0px;
  font-family: tahoma;
  color: #282828;
}
.cart {
  margin: 25px 100px;
  float: right;
  border: 1px solid #d8d8d8;
  padding: 10px 30px;
  background-color: white;
  -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
}
</style>
