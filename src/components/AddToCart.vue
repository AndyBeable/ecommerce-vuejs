<template>
<div class="counter-container">
  <button>-</button>
  <span>0</span>
  <button>+</button>
</div>
</template>

<script>
export default {
  name: "AddToCart"
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
}
span {
  font-weight: 700;
  color: #000;
}
</style>
