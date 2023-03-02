<template lang="">
    <div id="products" class="container ">
        <div class="row">
            <h4>Productos relacionados</h4>
        </div>
        <div class="row">
            <div class="col" v-for="product in products" :key="product.id">
                <ProductCard :product="product" :select="select"/>
            </div>
        </div>
    </div>
</template>
<script>
import ProductCard from "./ProductCard.vue";

export default {
    components: {
        ProductCard
    },
    props: {
        products: {
            type: Array,
            required: true
        },
        select: {
            type: Function,
            required: true
        }
    },
    setup() {
        
    }
}
</script>
<style lang="">
    
</style>