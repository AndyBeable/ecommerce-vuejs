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

      <div class="price-container">
        <div class="sale">
          <p class="price">{{product.price}}</p>
         <p class="discount">50%</p>
        </div>
        <p class="previous-price">$250.00</p>
      </div>

    </div>
  <AddToCart />
</div>
</template>

<script>
import AddToCart from "./AddToCart"

export default {
  name: "ProductDetails",
  components: {AddToCart},
  props: ['product']
}
</script>

<style scoped lang="scss">
.details-container {
  padding: 1rem;
}

.details-copy {
  margin-bottom: 2rem;
}
.titles {
  h5 {
    color: var(--orange);
    text-transform: uppercase;
    letter-spacing: 1.5px;
    margin-bottom: 1rem;
  }
  h1 {
    margin-bottom: 1rem;
  }
}

.description {
  margin-bottom: 2.5rem
}

.price-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.sale {
  display: flex;
  align-items: center;
  gap: 1rem;

}

.price {
  color: var(--black);
  font-weight: 700;
  font-size: 40px;
}
.discount {
  color: var(--orange);
  font-weight: 700;
  background: hsl(26, 100%, 55%, .2);
  padding: 3px 6px;
  border-radius: 3px;
}

.previous-price {
  font-weight: 700;
  text-decoration: line-through;
  color: #B6BCC8;
}


</style>
