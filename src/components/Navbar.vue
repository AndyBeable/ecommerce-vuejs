<template>
<header :class="{ 'scrolled-nav' : scrolledNav}">
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

  <div class="icon">
    <i @click="toggleMobileNav" v-show="mobile" class="fas fa-bars" :class="[mobileNav ? 'fa-times' :'fa-bars' ]"></i>
  </div>


  <transition name="mobile-nav">

    <ul v-show="mobileNav" class="dropdown-nav">



      <li><router-link class="link" :to="{name: 'Home'}">Home</router-link></li>
      <li><router-link class="link" :to="{name: ''}">Collection</router-link></li>
      <li><router-link class="link" :to="{name: ''}">Men</router-link></li>
      <li><router-link class="link" :to="{name: ''}">Women</router-link></li>
      <li><router-link class="link" :to="{name: ''}">About</router-link></li>
      <li><router-link class="link" :to="{name: ''}">Contact</router-link></li>
    </ul>

  </transition>

</nav>
</header>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      scrolledNav: null,
      mobile: null,
      mobileNav: null,
      windowWidth: null
    }
  },
  created() {
    window.addEventListener('resize', this.checkScreen);
    this.checkScreen()
  },
  methods: {
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav
    },

    checkScreen() {
      this.windowWidth = window.innerWidth
      if(this.windowWidth <= 750) {
        this.mobile = true
        return
      }
      this.mobile = false;
      this.mobileNav = false
      return
    }
  }
}
</script>

<style scoped lang="scss">

header {
  background-color: #fff;
  z-index: 99;
  width: 100%;
  position: fixed;
  transition: 0.5s ease all;


  nav {
    position: relative;
    display: flex;
    flex-direction: row;
    padding: 12px 0;
    transition: 0.5s ease all;
    width: 90%;
    margin: 0 auto;
    @media(min-width: 1140px) {
      max-width: 1140px;
    }
    ul,
    .link {
      font-weight: 700;
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
      &:hover {
        color: #000;
        border-color: #000;
      }
    }
    .branding {
      display: flex;
      align-items: center;

      img {
        width: 150px;
        transition: 0.5s ease all;
      }
    }

    .navigation {
      display: flex;
      align-items: center;
      flex: 1;
      justify-content: flex-end;
    }
    .icon {
      display: flex;
      align-items: center;
      position: absolute;
      top: 0;
      right: 24px;
      height: 100%;

      i {
        cursor: pointer;
        font-size: 24px;
        transition: 0.8s ease all;
        color: #69797D
      }
    }
    .dropdown-nav {
      display: flex;
      flex-direction: column;
      position: fixed;
      width: 100%;
      max-width: 250px;
      height: 100%;
      background-color: white;
      top: 0;
      left: 0;

      li {
        margin-left: 0;
        .link {
          color: #000;
        }
      }
    }
    .mobile-nav-enter-active,
    .mobile-nav-leave-active {
      transition: 1s ease all;
    }

    .mobile-nav-enter-from,
    .mobile-nav-leave-to {
      transform: translateX(-250px);
    }
    .mobile-nav-enter-to {
      transform: translateX(0);
    }
  }
}
</style>
