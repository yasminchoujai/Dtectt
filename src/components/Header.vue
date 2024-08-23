<template>
  <header class="header">
    <div class="logo-container">
      <img src="../assets/logo.png" alt="Logo" class="imglogo" />
    </div>
    <nav class="nav">
      <ul v-if="!isMobileView">
        <li><router-link to="/" class="nav-link">Home</router-link></li>
        <li><router-link to="/product" class="nav-link">Product</router-link></li>
        <li><router-link to="/contact" class="nav-link">Contact</router-link></li>
      </ul>
    </nav>
    <div class="auth-buttons" v-if="!isMobileView">
      <router-link to="/signin" class="call-me">Sign in</router-link>
      <router-link to="/signup" class="call-me">Sign up</router-link>
    </div>
    <hamburger-menu v-if="isMobileView"></hamburger-menu>
  </header>
</template>

<script>
import HamburgerMenu from '@/components/HamburgerMenu.vue'

export default {
  name: 'Header',
  components: {
    HamburgerMenu
  },
  data() {
    return {
      isMobileView: false
    }
  },
  created() {
    this.checkViewport()
    window.addEventListener('resize', this.checkViewport)
  },
  methods: {
    checkViewport() {
      this.isMobileView = window.innerWidth <= 768
    }
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.checkViewport)
  }
}
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding-top: 40px;
  padding-bottom: 20px;
  font-family: 'Poppins', sans-serif;
  width: 100%;
  background: #289bb6;
}

.logo-container {
  display: flex;
  align-items: center;
}

.imglogo {
  width: 32px;
  height: 32px;
  margin-right: 90px;
}

.nav ul {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav ul li {
  margin: 0 30px;
}

.nav-link {
  color: white;
  text-decoration: none;
  font-size: 16px;
  transition: 0.2s;
  font-size: 16px;
  padding: 8px 15px;
  transition:
    width 0.3s ease 0s,
    left 0.3s ease 0s;
}

.nav-link {
  color: white;
  position: relative;
}

.nav-link::after {
  content: '';
  background-color: white;
  position: absolute;
  bottom: 0;
  left: 0;
  height: 1px;
  width: 0;
  transition: 0.2s;
}

.nav-link:hover,
.nav-link:focus {
  color: white;
}

.nav-link:hover::after,
.nav-link:focus::after {
  background-color: white;
  width: 100%;
}

.auth-buttons {
  display: flex;
  align-items: center;
  font-size: 16px;
  transition: 0.2s;
  margin-left: 90px;
}

.call-me {
  background-color: #87c9bf;
  padding: 10px 20px;
  color: white;
  border-radius: 20px;
  margin-left: 20px;
  text-decoration: none;
  cursor: pointer;
  position: relative;
}
.call-me:hover {
  background-color: #abdee4;
  color: #135161;
}

@media (max-width: 768px) {
  .nav,
  .auth-buttons {
    display: none;
  }
}
</style>
