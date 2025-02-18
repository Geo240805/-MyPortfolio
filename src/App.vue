<template>
  <div id="app">
    <header>
      <nav>
        <div class="logo">Portafolio</div>
        <div class="menu-toggle" @click="toggleMenu">&#9776;</div>
        <ul :class="['nav-links', { 'active': menuOpen }]">
          <li><a href="#" @click="scrollToSection('HOMERUN')">Home</a></li>
          <li><a href="#" @click="scrollToSection('ABOUTME')">About</a></li>
          <li><a href="#" @click="scrollToSection('GALERIAP')">Gallery</a></li>
          <li><a href="#" @click="scrollToSection('CONTACTOFORMULARIO')">Contact</a></li>
        </ul>
      </nav>
    </header>

    <HomeComponent />

    <!-- Footer -->
    <footer>
      <div class="footer-container">
        <div class="footer-section">
          <h3>About us</h3>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Distinctio doloremque porro molestias.</p>
        </div>
        <div class="footer-section">
          <h3>Quick Links</h3>
          <ul>
            <li><a href="#" @click="scrollToSection('HOMERUN')">Home</a></li>
            <li><a href="#" @click="scrollToSection('ABOUTME')">About me</a></li>
            <li><a href="#" @click="scrollToSection('GALERIAP')">Gallery</a></li>
            <li><a href="#" @click="scrollToSection('CONTACTOFORMULARIO')">Contact</a></li>
          </ul>
        </div>
        <div class="footer-section">
          <h3>Contact</h3>
          <p>Email: geovannyed.pe.va@gmail.com</p>
          <p>Phone: (984) 164 0454</p>
          <p>Address: Playa del Carmen, MX</p>
        </div>
      </div>
      <div class="footer-bottom">
        <p>© 2025. By Geovanny Peech. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script>
import HomeComponent from './components/HomeComponent.vue';

export default {
  name: 'App',
  components: {
    HomeComponent
  },
  data() {
    return {
      menuOpen: false
    };
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
    scrollToSection(id) {
      const section = document.getElementById(id);
      if (section) {
        window.scrollTo(0, 0);
        section.scrollIntoView({ behavior: 'smooth' });
        this.menuOpen = false;
      }
    }
  }
};
</script>

<style>
body {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  text-align: center;
}

/* --- ESTILOS DE LA BARRA DE NAVEGACIONNN --- */
header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #1f2a38;
  color: white;
  padding: 25px 40px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  z-index: 1000;
}

nav {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-size: 25px;
  font-weight: bold;
  color: white;
  margin-left: 200px;
}

.menu-toggle {
  display: none;
  font-size: 30px;
  cursor: pointer;
  color: white;
  margin-right: 20px;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 20px;
  margin: 0;
  padding: 0;
  margin-right: 200px;
}

.nav-links li {
  display: inline;
}

.nav-links a {
  color: white;
  text-decoration: none;
  font-size: 15px;
}

/* NAVBAR RESPONSIVA EN FORMA DE LISTA */
@media (max-width: 768px) {
  .menu-toggle {
    display: block;
    margin-right: 85px;
  }

  .logo {
  margin-left: 10px;
  }


  .nav-links {
    display: none;
    flex-direction: column;
    position: absolute;
    top: 60px;
    left: -35px;
    width: 100%;
    background-color: #1f2a38;
    text-align: center;
    padding: 20px 0;
  }

  .nav-links.active {
    display: flex;
  }

  .nav-links li {
    margin: 10px 0;
  }
}

/* --- LOS ESTILOS PARA EL FOOTER --- */
footer {
  background-color: #1f2a38;
  color: white;
  padding: 40px 0;
  text-align: center;
  margin-top: 50px;
}

.footer-container {
  display: flex;
  justify-content: space-around;
  align-items: start;
  max-width: 1000px;
  margin: auto;
}

.footer-section {
  flex: 1;
  padding: 10px;
}

.footer-section h3 {
  color: #42a5f5;
}

.footer-section ul {
  list-style: none;
  padding: 0;
}

.footer-section ul li a {
  text-decoration: none;
  color: white;
}

.footer-bottom {
  margin-top: 20px;
  font-size: 14px;
}
</style>
