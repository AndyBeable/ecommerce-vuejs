<template>
<header>
<nav>
   <div class="nav_left">
      <div class="icon">
         <i @click="toggleMobileNav" v-show="mobile" class="fas fa-bars" :class="[mobileNav ? 'fa-times' :'fa-bars' ]"></i>
      </div>
      <div class="branding">
        <img src="@/assets/logo.svg" alt="Logo">
      </div>
   </div>
   <div class="nav_right">
      <div class="cart">
        <img src="@/assets/icon-cart.svg" alt="">
      </div>

      <div class="avatar">
        <img src="@/assets/image-avatar.png" alt="" class="avatar-thumb">
      </div>
   </div>

  <ul v-show="!mobile" class="navigation">
    <li><router-link class="link" :to="{name: 'Home'}">Home</router-link></li>
    <li><router-link class="link" :to="{name: ''}">Collection</router-link></li>
    <li><router-link class="link" :to="{name: ''}">Men</router-link></li>
    <li><router-link class="link" :to="{name: ''}">Women</router-link></li>
    <li><router-link class="link" :to="{name: ''}">About</router-link></li>
    <li><router-link class="link" :to="{name: ''}">Contact</router-link></li>
  </ul>




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
    gap: 1rem;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
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
    .nav_left {
      display: flex;
      gap: 1rem;
      align-items: center;

    }

    .icon {
      width: 24px;
    }

    .nav_right {
      display: flex;
      align-items: center;
      gap: 1rem;

      & .avatar-thumb {
        width: 100%;
      }
    }

    .link {
      font-size: 14px;
      font-weight: 500;
      transition: 0.5s ease all;
      padding-bottom: 4px;
      border-bottom: 3px solid transparent;
      &:hover {
        color: var(--black);
        border-color: var(--orange);
      }
    }



    .navigation {
      display: flex;
      align-items: center;
      flex: 1;
      justify-content: flex-end;
    }
    .icon {
      //display: flex;
      //align-items: center;
      //position: absolute;
      //top: 0;
      //right: 24px;
      //height: 100%;

      i {
        cursor: pointer;
        font-size: 24px;
        transition: 0.8s ease all;
        color: #69797D
      }
    }

    .avatar {
      width: 25px;
      height: auto;
    }
    .dropdown-nav {
      display: flex;
      flex-direction: column;
      position: fixed;
      width: 100%;
      max-width: 250px;
      height: 100%;
      background-color: white;
      top: 50px;
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
