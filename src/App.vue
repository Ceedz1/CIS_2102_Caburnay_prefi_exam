<template>
  <div>
    <header>
      <button class="btn success" v-on:click="navigateTo('products')">Products</button>
      <button class="btn success" v-on:click="navigateTo('cart')"> Cart</button>
      <button class="btn success">{{cart.length}} in cart</button>
    </header>
    <hr>
    <div v-if="page === 'cart'">
      <Cart v-on:removeItemFromCart="removeItemFromCart" :cart="cart" />
    </div>
    <div v-if="page === 'products'">
      <Products v-on:addItemToCart="addItemToCart" />
    </div>
    
  </div>
</template>

<script>
import Products from "./components/Products.vue";
import Cart from "./components/Cart.vue";

export default {
  name: "App",
  data: () => {
    return {
      page: "products",
      cart: [],
      details: []
    };
  },
  methods: {
    addItemToCart(product) {
      this.cart.push(product);
    },
    removeItemFromCart(product) {
      this.cart.splice(this.cart.indexOf(product), 1);
    },
    navigateTo(page) {
      this.page = page;
    }
  },
  components: { Products, Cart }
};
</script>

<style>
body {
  margin: 0;
}

.products {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
}

.products button {
  padding: 10px;
  background-color: rgb(95, 95, 95);
  color: white;
  outline: none;
  border: none;
  cursor: pointer;
  

}

</style>

<style scoped>
header {
  height: 60px;
  text-align: left;
  font-size: 20px;
  padding-top: 20px;
}


.btn {
  border: none;
  background-color: inherit;
  padding: 14px 28px;
  font-size: 20px;
  cursor: pointer;
  display: inline-block;
}
.btn:hover{
  color: orange;
  transition: .5ms;
}

.success {color: rgb(53, 53, 53);}


</style>
