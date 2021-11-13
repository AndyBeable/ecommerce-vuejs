<template>
  <div class="wrapper">
<ProductGallery />
  </div>
</template>

<script>
import ProductGallery from "./ProductGallery"
export default {
  name: "ProductCard",
  components: {ProductGallery}
}
</script>

<style scoped>
.wrapper {
padding-top: 3rem;
}
</style>
