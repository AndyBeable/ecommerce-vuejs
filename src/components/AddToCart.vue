<template>
<div class="counter-container">
  <button @click="removeFromCart">-</button>
  <span>{{counter}}</span>
  <button @click="addToCart">+</button>
</div>
</template>

<script>
export default {
  name: "AddToCart",
  data() {
    return {
      counter: 0
    }
  },
  methods: {
    removeFromCart() {
      this.counter = this.counter - 1;
    },
    addToCart() {
      this.counter = this.counter + 1;
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
