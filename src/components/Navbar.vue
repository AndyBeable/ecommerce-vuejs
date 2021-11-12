<template>
<header :class="{ 'scrolled-nav' : scrollPosition}">
<nav>
  <div class="branding">
    <img src="@/assets/logo.svg" alt="Logo">
  </div>
  <ul v-show="!mobile" class="navigation">
    <li><router-link class="link" :to="{name: 'Home'}">Home</router-link></li>
    <li><router-link class="link" :to="{name: ''}">Collection</router-link></li>
    <li><router-link class="link" :to="{name: ''}">Men</router-link></li>
    <li><router-link class="link" :to="{name: ''}">Women</router-link></li>
    <li><router-link class="link" :to="{name: ''}">About</router-link></li>
    <li><router-link class="link" :to="{name: ''}">Contact</router-link></li>
  </ul>
</nav>
</header>
</template>

<script>
export default {
  name: "Navbar"
}
</script>

<style scoped>

</style>
