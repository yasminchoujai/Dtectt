<template>
  <div class="hamburger-menu">
    <div class="menu-icon" @click="toggleMenu">
      <span :class="{ open: isMenuOpen }"></span>
      <span :class="{ open: isMenuOpen }"></span>
      <span :class="{ open: isMenuOpen }"></span>
    </div>
    <transition name="slide-fade">
      <div v-if="isMenuOpen" class="menu-sidebar" @click.self="toggleMenu">
        <ul>
          <li><router-link to="/" @click="toggleMenu" class="menu-link">Home</router-link></li>
          <li>
            <router-link to="/product" @click="toggleMenu" class="menu-link">Product</router-link>
          </li>
          <li>
            <router-link to="/contact" @click="toggleMenu" class="menu-link">Contact</router-link>
          </li>
        </ul>
        <div class="auth-buttons">
          <router-link to="/signin" @click="toggleMenu" class="auth-button">Sign in</router-link>
          <router-link to="/signup" @click="toggleMenu" class="auth-button">Sign up</router-link>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
    handleScroll() {
      if (this.isMenuOpen) {
        this.isMenuOpen = false
      }
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style scoped>
.hamburger-menu {
  position: relative;
  z-index: 1500;
}

.menu-icon {
  display: flex;
  flex-direction: column;
  cursor: pointer;
  padding: 10px;
}

.menu-icon span {
  width: 28px;
  height: 3px;
  background-color: #ffffff;
  margin: 5px 0;
  transition: all 0.3s ease;
  border-radius: 2px;
}

.menu-icon span.open:nth-child(1) {
  transform: rotate(45deg) translate(6px, 6px);
}

.menu-icon span.open:nth-child(2) {
  opacity: 0;
}

.menu-icon span.open:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

.menu-sidebar {
  position: fixed;
  top: 0;
  right: 0;
  width: 250px; /* Smaller width for a cleaner design */
  height: 100vh;
  background-color: #2c3e50;
  padding: 40px 20px;
  box-shadow: -4px 0 16px rgba(0, 0, 0, 0.4);
  transition: transform 0.3s ease;
  display: flex;
  flex-direction: column;
  text-align: left;
}

.menu-sidebar ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.menu-sidebar ul li {
  margin-bottom: 20px;
}

.menu-sidebar .menu-link {
  color: #ecf0f1;
  text-decoration: none;
  font-size: 18px;
  font-family: 'Roboto', sans-serif;
  transition: color 0.3s ease;
  display: block;
  padding: 10px;
}

.menu-sidebar .menu-link:hover {
  color: #87c9bf;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 5px;
}

.auth-buttons {
  display: flex;
  flex-direction: column;
}

.auth-button {
  background-color: #87c9bf;
  border: none;
  padding: 12px;
  color: white;
  cursor: pointer;
  font-size: 16px;
  border-radius: 20px;
  margin-bottom: 10px;
  text-decoration: none;
  display: block;
  text-align: left;
  transition:
    background-color 0.3s ease,
    transform 0.3s ease;
  width: 70px;
}

.auth-button:hover {
  background-color: #82e9de;
  transform: translateY(-2px);
}

/* Slide-fade transition */
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.4s ease;
}

.slide-fade-enter,
.slide-fade-leave-to {
  transform: translateX(100%);
  opacity: 0;
}
</style>
