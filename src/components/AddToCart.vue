<template>
  <div>
<div class="quantity-container">
  <button @click="decreaseQuantity">-</button>
  <span>{{quantity}}</span>
  <button @click="increaseQuantity">+</button>
</div>
    <button class="add-to-checkout">
      <img src="../assets/icon-cart.svg" alt="">
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

  img {
    height: 24px;
    margin-right: 1rem;
  }
}
</style>
