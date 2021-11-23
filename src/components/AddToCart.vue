<template>
  <div>
<div class="quantity-container">
  <button @click="decreaseQuantity">-</button>
  <span>{{quantity}}</span>
  <button @click="increaseQuantity">+</button>
</div>
    <button class="add-to-checkout">
      <svg width="22" height="20" xmlns="http://www.w3.org/2000/svg"><path d="M20.925 3.641H3.863L3.61.816A.896.896 0 0 0 2.717 0H.897a.896.896 0 1 0 0 1.792h1l1.031 11.483c.073.828.52 1.726 1.291 2.336C2.83 17.385 4.099 20 6.359 20c1.875 0 3.197-1.87 2.554-3.642h4.905c-.642 1.77.677 3.642 2.555 3.642a2.72 2.72 0 0 0 2.717-2.717 2.72 2.72 0 0 0-2.717-2.717H6.365c-.681 0-1.274-.41-1.53-1.009l14.321-.842a.896.896 0 0 0 .817-.677l1.821-7.283a.897.897 0 0 0-.87-1.114ZM6.358 18.208a.926.926 0 0 1 0-1.85.926.926 0 0 1 0 1.85Zm10.015 0a.926.926 0 0 1 0-1.85.926.926 0 0 1 0 1.85Zm2.021-7.243-13.8.81-.57-6.341h15.753l-1.383 5.53Z"  fill-rule="nonzero"/></svg>
      Add to cart
    </button>
  </div>
</template>

<script>
export default {
  name: "AddToCart",
  data() {
    return {
      quantity: 0
    }
  },
  methods: {
    decreaseQuantity() {
      if(this.quantity <= 0 ) {
        return
      }
      this.quantity = this.quantity-= 1;
    },
    increaseQuantity() {
      this.quantity = this.quantity+= 1;
    }
  }
}
</script>

<style scoped lang="scss">
.quantity-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: hsl(223, 64%, 98%);
  padding: 1rem 1rem;
  border-radius: 6px;
  margin-bottom: 1rem;
}

button {
  font-size: 26px;
  font-weight: 700;
  /*color: #FF7E1B;*/
  border: none;
  background: hsl(223, 64%, 98%);
  cursor: pointer;
}
span {
  font-weight: 700;
  color: var(--black);
}

.add-to-checkout {
  display: flex;
  justify-content: center;
  align-items: center;
  background: var(--orange);
  color: var(--white);
  font-size: 18px;
  letter-spacing: 1.2px;
  width: 100%;
  padding: 1rem;
  border-radius: 7px;
  box-shadow: 0px 2px 11px 4px rgba(0,0,0,0.34);
  transition: .2s ease-in-out all;

  &:hover {
    opacity: .8;
  }

  svg {
    fill: var(--white);
    height: 24px;
    margin-right: 1rem;
  }
}
</style>
