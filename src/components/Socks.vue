<template>

    <div class="cart">Cart({{ cartState.cart }})</div>

    <div class="product-display">
        <div class="product-container">
          <div class="product-image">
            <img :src="socks.img" alt="Socks image">
          </div>
          <div class="product-info">
            <h1>{{ socks.name }}</h1>
            <p>{{ socks.description }}, For more check our <a :href="externData.links.google">this page</a></p>
            <p v-if="socks.inventory > 10">In Stock</p>
            <p v-else-if="socks.inventory <= 10 && socks.inventory > 0">Almost out of stock!</p>
            <p v-else>Out Of Stock</p>
            <p v-if="socks.onSale">On Sale</p>
            <ul>
              <li :key="detail.index" v-for="detail in socks.details">{{ detail }}</li>
            </ul>
            <span :key="variant.id" v-for="variant in socks.variants" @mouseover="updateImage(variant.image)">{{variant.color}}</span>
            <br/>
            <span :key="size.index" v-for="size in socks.sizes">{{size}}</span>
            <br/>
            <button class="button" @click="addToCart">Add to Cart</button>
            <button v-if="cartState.cart > 0" class="button" @click="removeFromCart">Remove</button>
          </div>
        </div>
      </div>
</template>

<script>
import { reactive } from 'vue';
export default {

  setup(){

    const addToCart = () => {
      cartState.cart += 1;
    }
    const removeFromCart = () => {
      cartState.cart -= 1;
    }
    const updateImage = (variantImage) => {
      socks.img = variantImage
    }


    const cartState = reactive({
      cart: 0,
    })
    const externData = reactive({
      links: {
        google: 'https://google.com'
        }
    })
    const productData = reactive({
      products:{
        socks: {
          name: 'Socks',
          description: 'Warm Green Socks',
          img: '/socks_green.jpg',
          inventory: 9,
          onSale: true,
          details: ['50% cotton', '30% wool', '20% polyester'],
          sizes: ['small', 'medium', 'large'],
          variants: [
            { id: 2234, color: 'green', image: '/socks_green.jpg' },
            { id: 2235, color: 'blue', image: '/socks_blue.jpg' }
          ]
        },
      }
    });

    const socks = productData.products.socks;

    return{
      productData,
      externData,
      socks,
      cartState,
      addToCart,
      updateImage,
      removeFromCart

    }
  },
}
</script>

<style scoped>
h1 {
  font-size: 50px;
}
p {
  font-size: 22px;
}
li {
  font-size: 18px;
}
ul {
  list-style-type: none;
}

span{
  margin-right: 16px;
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

img {
  border: 2px solid #d8d8d8;
  width: 70%;
  margin: 40px;
  padding: 15px;
  -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
}

.button {
  margin: 30px;
  background-color: #39495c;
  border-radius: 5px;
  font-size: 18px;
  width: 160px;
  height: 60px;
  color: white;
  padding: 20px;
  box-shadow: inset 0 -0.6em 1em -0.35em rgba(0, 0, 0, 0.17),
    inset 0 0.6em 2em -0.3em rgba(255, 255, 255, 0.15),
    inset 0 0 0em 0.05em rgba(255, 255, 255, 0.12);
  text-align: center;
  cursor: pointer;
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
