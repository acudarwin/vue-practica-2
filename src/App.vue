<script setup>
import HeaderLayout from './layouts/HeaderLayout.vue'
import FooterLayout from './layouts/FooterLayout.vue'
import ContainerLayout from './layouts/ContainerLayout.vue'
import ProductView from './views/ProductView.vue'
</script>
<template>
  <HeaderLayout />
  <ContainerLayout>
    <ProductView/>
  </ContainerLayout>
  
  <FooterLayout />  
</template>

<style scoped>

</style>
