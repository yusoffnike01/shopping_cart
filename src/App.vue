<template>
 
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div class="container">
    <div class="row">
<div class="col-md-7">
<div class="row">


  <div :key="product.id" class="col-md-6" v-for="product in products">
    <product :isIncart=isIncart(product) v-on:add-to-cart="addcart(product)" :product="product"></product>
  </div>
</div>
<div class="col-md-5 my-5">
<cart  v-on:pay="pay()" v-on:remove-cart="removecart($event)" :items="cart"></cart>

</div>

</div>

    </div>
    </div>
</template>

<script>

import products from '@/products.json';
import Product from '@/components/Product.vue';
import cart from '@/components/cart.vue';
export default {
  name: 'App',
  components:{


Product,
cart


  },
  data(){
    return{
      products,
      cart:[]
      
       
    }
  },
  methods:
  {
    addcart(product)
    {
      this.cart.push(product)
    },

    isIncart(product)
    {
      const item=this.cart.find(item=>item.id===product.id)
   
   if(item)
   {
     return true
   }
   return false
   
   
   },
   removecart(product)
   {
     this.cart=this.cart.filter(item=> item.id!==product.id)
     console.log('wsww')
   },
   pay()
   {
     this.cart=[]
     alert('Shopping Completed')
   }
  }
   
}
</script>

<style scoped >
body{
  background-color: aliceblue;
}
</style>
