<template>
  <section class="hero">
    <div class="hero-content">
      <h1>La Plataforma AI para tu organización</h1>
      <p>Obtén todos los beneficios de las mejores herramientas AI pero con una mucho mejor eficiencia financiera.</p>
      <router-link to="/about" class="hero-button">Descubre Más</router-link>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HeroSection',
};
</script>

<style scoped>
.hero {
  width: 100%;
  height: 65vh;
  background: url('/assets/hero-background.jpg') center center/cover no-repeat; /* Replace with your image path */
  display: flex;
  align-items: center;
  background: linear-gradient(0deg, rgba(228,221,211,1) 0%, rgba(253,253,253,1) 97%);
  justify-content: center;
}

.hero-content {
  width: 100vh;
  text-align: center;
  color: #000;
  padding: 0 1rem;
}

.hero h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.hero p {
  font-size: 1.5rem;
  margin-bottom: 2rem;
}

.hero-button {
  padding: 0.75rem 2rem;
  background-color: #007aa3;
  color: #fff;
  border: none;
  border-radius: 30px;
  text-decoration: none;
  font-size: 1rem;
  transition: background-color 0.3s ease;
}

.hero-button:hover {
  background-color: #1790b9;
}

/* Responsive */
@media (max-width: 768px) {
  .hero h1 {
    font-size: 2.5rem;
  }

  .hero p {
    font-size: 1.2rem;
  }
}
</style>