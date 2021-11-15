<template>
  <div id="app">
    <Navbar />
    <ProductCard />
  </div>
</template>

<script>
import Navbar from "./components/Navbar"
import ProductCard from "./components/ProductCard"

export default {
  name: 'App',
  components: {
    ProductCard,
    Navbar
  },
  data() {
    return {
      cart: 0
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Kumbh+Sans:wght@400;700&display=swap');
:root {
  --white: hsl(0, 0%, 100%);
  --orange: hsl(26, 100%, 55%);
  --grey: hsl(192, 9%, 45%);
  --black: hsl(220, 13%, 13%)
}

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Kumbh Sans';
}
p {
  color: var(--grey);
  line-height: 1.5rem;
  letter-spacing: 1.5px;
}
</style>
