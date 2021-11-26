<template>
  <div>
    <div class="hcon">
    <h1>Cart</h1>
    </div>
    <div class="products">
      
      <div v-for="(product, index) in cart" :key="index">
      <div class="card">
        <img :src="product.img" />
        <div class="container">
          <h3><b>{{product.name}}</b></h3>
          <p>{{product.para}}</p>
          <div class="cost">{{product.price}}</div>
          
          <hr>
          
          <button v-on:click="removeItemFromCart(product)">Remove</button> 
        </div> 
      </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["cart"],
  methods: {
    removeItemFromCart(product) {
      this.$emit("removeItemFromCart", product);
    }
  }
};
</script>

<style>
.hcon {
  width: 1090px;
  display: flex;
  flex-wrap: wrap;
  margin: 0 auto;
 
}
</style>