<template>
    <div class="product-display">
        <div class="product-container">
          <div class="product-image">
            <!-- image goes here -->
          </div>
          <div class="product-info">
            <h1>{{ productData.products.socks.name }}</h1>
            <p>{{ productData.products.socks.description }}</p>
          </div>
        </div>
      </div>
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

<style scoped>
h1 {
  font-size: 50px;
}
p {
  font-size: 22px;
}

.product-display {
  display: flex;
  flex-direction: column;
  padding: 1rem;
}

.product-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.product-image,
.product-info {
  width: 50%;
}
</style>
