<template>
<div class="counter-container">
  <button @click="decreaseQuantity">-</button>
  <span>{{quantity}}</span>
  <button @click="increaseQuantity">+</button>
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
      this.quantity = this.quantity - 1;
    },
    increaseQuantity() {
      this.quantity = this.quantity + 1;
    }
  }
}
</script>

<style scoped>
.counter-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: hsl(223, 64%, 98%);
  padding: 1rem 1rem;
  border-radius: 6px;
}

button {
  font-size: 26px;
  font-weight: 700;
  color: #FF7E1B;
  border: none;
  background: hsl(223, 64%, 98%);
  cursor: pointer;
}
span {
  font-weight: 700;
  color: #000;
}
</style>
