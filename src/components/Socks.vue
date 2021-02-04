<template>
    <h1>{{ productData.products.socks.name }}</h1>
    <p>{{ productData.products.socks.description }}</p>
</template>

<script>
import { reactive } from 'vue';
export default {

  setup(){

    const productData = reactive({
      products:{
        socks: {
          name: 'Socks',
          description: 'Warm Green Socks'
        },
      }
    });

    return{
      productData

    }
  },
  
  name: 'Socks',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
