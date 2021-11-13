<template>
<header :class="{ 'scrolled-nav' : scrollPosition}">
<nav>
  <div class="branding">
    <img src="@/assets/logo.svg" alt="Logo">
  </div>
  <div class="icon">
    <i @click="toggleMobileNav" v-show="mobile" class="fas fa-bars" :class="[mobileNav ? 'fa-bars' :'fa-bars' ]"></i>
  </div>
  <transition name="mobile-nav">
    <ul v-show="mobileNav" class="navigation">
      <li><router-link class="link" :to="{name: 'Home'}">Home</router-link></li>
      <li><router-link class="link" :to="{name: ''}">Collection</router-link></li>
      <li><router-link class="link" :to="{name: ''}">Men</router-link></li>
      <li><router-link class="link" :to="{name: ''}">Women</router-link></li>
      <li><router-link class="link" :to="{name: ''}">About</router-link></li>
      <li><router-link class="link" :to="{name: ''}">Contact</router-link></li>
    </ul>

  </transition>
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
  name: "Navbar",
  data() {
    return {
      scrollPosition: null,
      mobile: true,
      mobileNav: true,
      windowWidth: null
    }
  },
  methods: {
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav
    }
  }
}
</script>

<style scoped>
header {
  background-color: lightblue;
  z-index: 99;
  width: 100%;
  position: fixed;
  transition: .5s ease all;
}

nav {
  display: flex;
  flex-direction: row;
  padding: 12px 0;
  transition: .5s ease all;
  width: 90%;
  margin: 0 auto;
  position: relative;
}

@media(min-width: 1140px) {
  nav {
    max-width: 1140px;
  }
}

nav ul, .link {
  font-width: 500;
  color: #000;
  list-style: none;
  text-decoration: none;
}
li {
  text-transform: uppercase;
  padding: 16px;
  margin-left: 16px;
}
.link {
  font-size: 14px;
  transition: 0.5s ease all;
  padding-bottom: 4px;
  border-bottom: 1px solid transparent;
}

.link:hover {
  color: #000;
  border-color: #000
}

.branding {
  display: flex;
  align-items: center;
}

img {

  transition: .5s ease all;
}

.navigation {
  display: flex;
  align-items: center;
  flex: 1;
  justify-content: flex-start;
}

.icon {
  display: flex;
  position: absolute;
  align-items: center;
  top: 0;
  left: -25px;
  height: 100%;
}

.icon-active {

}
i {
  cursor: pointer;
  font-size: 24px;
  transition: .8s ease all;
}

.dropdown {
  display: flex;
  flex-direction: column;
  position: fixed;
  width: 100%;
  max-width: 250px;
  height: 100%;
  background-color: red;
  top: 0;
  left: 0;
}

.dropdown li {
  margin-left: 0;
}


</style>
