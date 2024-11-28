<template>
  <header class="header">
    <nav class="nav container">
      <div class="logo">
        <a href="#" class="logo-text">Ketza</a>
      </div>
      <div :class="['nav-menu', { 'active': isMenuOpen }]" ref="navMenu">
        <ul class="nav-list">
          <li class="nav-item">
            <a href="#" class="nav-link">Precios</a>
          </li>
          <li class="nav-item">
            <a href="#" class="nav-link">Plataforma</a>
          </li>
          <li class="nav-item">
            <a href="#" class="nav-link">Contacto</a>
          </li>
        </ul>
      </div>
      <div class="hamburger" @click="toggleMenu" :class="{ 'active': isMenuOpen }">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </nav>
    <!-- Optional Overlay for Mobile Menu -->
    <div v-if="isMenuOpen" class="overlay" @click="toggleMenu"></div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
  },
};
</script>

<style scoped>
/* Header Styles */
.header {
  width: 100%;
  position: sticky;
  top: 0;
  z-index: 1000;
  background-color: #fdfdfd;
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 6em;
  box-sizing: border-box;
  padding: 0 2em;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: bold;
  color: #333;
  text-decoration: none;
}

.nav-menu {
  display: flex;
}

.nav-list {
  display: flex;
  list-style: none;
}

.nav-item {
  margin-left: 1.5rem;
}

.nav-link {
  text-decoration: none;
  color: #333;
  position: relative;
  font-size: 1rem;
  transition: color 0.3s ease;
}

.nav-link::after {
  content: '';
  position: absolute;
  width: 0%;
  height: 2px;
  background-color: #333;
  left: 0;
  bottom: -5px;
  transition: all 0.3s ease-in-out;
}

.nav-link:hover::after {
  width: 100%;
}

.nav-link:hover {
  color: #000;
}

/* Hamburger Menu */
.hamburger {
  display: none;
  flex-direction: column;
  cursor: pointer;
  z-index: 1100;
}

.hamburger span {
  height: 3px;
  width: 25px;
  background: #333;
  margin-bottom: 5px;
  border-radius: 5px;
  transition: all 0.3s ease;
}

/* Hamburger Animation */
.hamburger.active span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.hamburger.active span:nth-child(2) {
  opacity: 0;
}

.hamburger.active span:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

/* Overlay */
.overlay {
  position: fixed;
  top: 60px; /* Height of the nav */
  left: 0;
  width: 100%;
  height: calc(100% - 60px);
  background: rgba(0, 0, 0, 0.5);
  z-index: 900;
  animation: fadeIn 0.3s ease;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Responsive */
@media (max-width: 768px) {
  .nav {
    padding: 0 1.5em;
    height: 4em;
  }

  .nav-menu {
    display: none;
    flex-direction: column;
    align-items: center;
    position: fixed;
    top: 60px;
    left: 0;
    width: 100%;
    height: calc(100% - 60px);
    background-color: #e4ddd3;
    padding: 2em;
    transition: transform 0.3s ease-in-out;
    transform: translateY(-100%);
  }

  .nav-menu.active {
    display: flex;
    transform: translateY(0);
  }

  .nav-list {
    flex-direction: column;
    width: 100%;
    padding: 2em 0;
  }

  .nav-item {
    margin: 1.5rem 0;
  }

  .nav-link {
    font-size: 1.2rem;
  }

  .hamburger {
    display: flex;
  }
}
</style>