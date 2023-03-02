<template lang="">
    <ProductDetail :product="currentProduct"></ProductDetail>
    <ProductList :products="filterProducts()" :select="setCurrentProduct"></ProductList>
</template>
<script>
import ProductDetail from '../components/ProducDetail.vue'
import ProductList from '../components/ProductList.vue'
import axios from 'axios';
import { ref } from 'vue';
export default {
    components: {
        ProductDetail,
        ProductList
    },
    setup() {
        const products = ref([]);
        const currentProduct = ref({});
        const setCurrentProduct = (id) => {
            currentProduct.value = products.value.find(product => product.id === id);
        }
        const filterProducts = () => {
            const id = currentProduct.value.id;
            return products.value.filter(product => product.id !== id);
        }
        const getProducts = async () => {
            const data = await axios.get('http://localhost:4000/Productos');
            products.value = data.data;
            setCurrentProduct(products.value[0].id)
        }

        getProducts();
        return {
            products,
            filterProducts,
            setCurrentProduct,
            currentProduct
        }
        
    }
}
</script>
<style lang="">
    
</style>