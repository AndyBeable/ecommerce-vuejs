<template>
  <div class="wrapper">
    <ProductGallery />
    <ProductDetails :product="product"/>
  </div>
</template>

<script>
import ProductGallery from "./ProductGallery"
import ProductDetails from "./ProductDetails"
export default {
  name: "ProductCard",
  components: {ProductDetails, ProductGallery},
  data() {
    return {
    product: {
      brand: 'Sneaker Company',
      item: 'Fall Limited Edition Sneakers',
      description: 'These low-profile sneakers are your perfect casual wear companion. Featuring a durable rubber outer sole, they\'ll withstand everything the weather can offer.\n',
      price: '$125.00'
    }
    }
  }
}
</script>

<style scoped>
.wrapper {
padding-top: 3rem;
}
</style>
