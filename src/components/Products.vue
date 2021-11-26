<template>
  <div>
    <div class="hcon">
    <h1>Products</h1>
    </div>

    <div class="products">
      <div v-for="(product, index) in products" :key="index">
      <div class="card">
        <img :src="product.img" />
        <div class="container">
          <h3><b>{{product.name}}</b></h3>
          <div class="cost">{{product.price}}</div>
          <hr>
          
          
          <button v-on:click="addItemToCart(product)">Add to Cart</button> 
           
        </div> 
      </div>
      </div>
    </div>
    
  </div>
</template>

<script>


export default {
  
  data: () => {
    return {
      products: [
        {
          id: 1, 
          name: "Bacon",
          price:"₱250.00",
          quantity:10, 
          para: " a cured meat product traditionally derived from pork belly",
          category: ["Meat"],
          img:'https://healthyrecipesblogs.com/wp-content/uploads/2018/01/oven-bacon-featured.jpg'
        },
        {
          id: 2, 
          name: "Fish",
          price:"₱150.00",
          quantity:5, 
          para: "fishmeal, fish body and liver oils, fish maw, isinglass",
          category: ["Seafood","Fresh"],
          img:'https://cdn-prod.medicalnewstoday.com/content/images/articles/322/322522/fresh-fish-on-ice.jpg'
        },
        {
          id: 3, 
          name: "Chicken",
          price:"₱200.00",
          quantity:9, 
          para: "Chicken wings are everybody's favorite for a reason.",
          category: ["Poultry","Fresh"],
          img:'https://www.seriouseats.com/thmb/t82X6N4ZwGkFZmWPuCjwT-osL3g=/1500x844/smart/filters:no_upscale()/20210714-potato-starch-fried-chicken-vicky-wasik-seriouseats-20-17e193a6bf274bba9091810a0b18ef89.jpg'
        },
        {
          id: 4, 
          name: "Beef",
          price:"₱300.00",
          quantity:11, 
          para: "flesh of mature cattle, as distinguished from veal",
          category: ["Meat"],
          img:'https://post.healthline.com/wp-content/uploads/2020/08/beef-update-1200x628-facebook-1200x628.jpg'
        },
        {
          id: 5, 
          name: "Soy Sauce",
          price:"₱50.00",
          quantity:0, 
          para: " made from a blend of soybeans and wheat",
          category: ["Sauce","Seasoning"],
          img:'https://www.tasteofhome.com/wp-content/uploads/2020/01/GettyImages-461879075.jpg?fit=700,1024'
        },
        {
          id: 9, 
          name: "Egg",
          price:"₱10.00",
          quantity:72,
          para: "the contents found inside eggs separated from the shell", 
          category: ["Dairy"],
          img:'https://cdn.britannica.com/94/151894-050-F72A5317/Brown-eggs.jpg'
        },
        {
          id: 11, 
          name: "Pork",
          price:"₱200.00",
          quantity:12, 
          para: "the most commonly consumed meat worldwide",
          category: ["Meat"],
          img:'https://www.seriouseats.com/thmb/yHg0KQZc928Iqbm8G-aOE91gJb0=/1500x1125/filters:fill(auto,1)/__opt__aboutcom__coeus__resources__content_migration__serious_eats__seriouseats.com__recipes__images__2016__02__20160208-sous-vide-pork-chop-guide-food-lab-37-9bfa2f9b8a464bccad99ea08423b9d8e.jpg'
        },
      ],
      
    };
  },
  methods: {
    addItemToCart(product) {
      this.$emit("addItemToCart", product);
    },
    
  },
  
};
</script>

<style>

.card{
  margin: 10px;
  border-radius: 10px 10px 10px 10px;
  width: 250px;
  height: 400px;
  box-shadow: 0 0 0 0 rgba(0,0,0,0.2);
  transition: 0.3s;
}
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}
.container {
  padding: 2px 16px;
}

.container button{
  border-radius: 5px 5px 5px 5px;
}
.container button:hover{
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}
.products{
 
  width: 1090px;
  display: flex;
  flex-wrap: wrap;
  margin: 0 auto;
}
.products img{
  width: 250px;
  height: 200px;
  padding: 1px 1px 1px;
  border-radius: 10px 10px 0 0;
}
.addtoCart button{
  padding: 5px 5px 5px 5px;
}
.hcon {
  width: 1090px;
  display: flex;
  flex-wrap: wrap;
  margin: 0 auto;
 
}

</style>