<template>
<div class="details-container">
  <header>
    <div class="titles">
    <h5>{{ product.brand }}</h5>
    <h1>{{ product.item }}</h1>
    </div>
  </header>
    <div class="details-copy">
      <p class="description">{{product.description}}</p>
      <p class="price">{{product.price}}</p>
    </div>
</div>
</template>

<script>
export default {
  name: "ProductDetails",
  props: ['product']
}
</script>

<style scoped lang="scss">
.details-container {
  padding: 1rem;
}
.titles {
  h5 {
    color: #FF7E1B;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    margin-bottom: 1rem;
  }
  h1 {
    margin-bottom: 1rem;
  }
}

.description {
  margin-bottom: 1.5rem
}
.price {
  color: #000;
  font-weight: 700;
  font-size: 40px;
}


</style>
