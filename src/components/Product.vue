<template>
    <div class="card my-5">

<div class="card-body">

    <h5 class="text-center card-title"> {{product.title}}</h5>
<p class="text-center text-muted card-text display-4">${{Number(product.price).toFixed(2)}}</p>
<button  :disable="isIncart" @click="$emit('add-to-cart',product)" class="btn btn-primary form-control">{{isIncart? 'Added to cart' : 'Add to cart'}}</button>


</div>


    </div>
</template>


<script>
export default {
    props:['product','isIncart']

}
</script>