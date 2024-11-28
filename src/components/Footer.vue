<template>
  <footer class="footer">
    <div class="footer-container">
      <div class="footer-section">
        <h3>Ketza</h3>
        <p>Conectando la AI con tu organización.</p>
      </div>
      <div class="footer-section">
        <h4>Navegación</h4>
        <ul>
          <li><router-link to="/">Inicio</router-link></li>
          <li><router-link to="/about">Acerca de</router-link></li>
          <li><router-link to="/services">Servicios</router-link></li>
          <li><router-link to="/pricing">Precios</router-link></li>
          <li><router-link to="/contact">Contacto</router-link></li>
        </ul>
      </div>
      <div class="footer-section">
        <h4>Legal</h4>
        <ul>
          <li><router-link to="/terms">Términos de servicio</router-link></li>
          <li><router-link to="/privacy">Política de privacidad</router-link></li>
          <li><router-link to="/sitemap">Mapa del sitio</router-link></li>
        </ul>
      </div>
      <div class="footer-section">
        <h4>Contacto</h4>
        <p>Av. Insurgentes Sur 1877</p>
        <p>Álvaro Obregón, CDMX</p>
        <p>Email: info@ketza.com</p>
      </div>
    </div>
    <div class="footer-bottom">
      <p>&copy; 2024 Ketza. Todos los derechos reservados.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
};
</script>

<style scoped>
.footer {
  background-color: #333;
  color: #fff;
  padding: 2rem 1rem;
}

.footer-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.footer-section {
  flex: 1 1 200px;
  margin-bottom: 1.5rem;
}

.footer-section h3,
.footer-section h4 {
  margin-bottom: 1rem;
}

.footer-section ul {
  list-style: none;
  padding: 0;
}

.footer-section ul li {
  margin-bottom: 0.5rem;
}

.footer-section a {
  color: #fff;
  text-decoration: none;
}

.footer-section a:hover {
  text-decoration: underline;
}

.social-media a {
  margin-right: 0.5rem;
}

.social-media img {
  width: 24px;
  height: 24px;
}

.footer-bottom {
  text-align: center;
  margin-top: 1rem;
  border-top: 1px solid #444;
  padding-top: 1rem;
}

/* Responsive */
@media (max-width: 768px) {
  .footer-container {
    flex-direction: column;
  }

  .footer-section {
    margin-bottom: 1rem;
  }
}
</style>