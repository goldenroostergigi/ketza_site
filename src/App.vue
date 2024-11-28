<template>
  <div id="app">
    <Header />
    <router-view />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
  },
};
</script>

<style>

/* Apply the font globally to the entire app */
body {
  font-family: 'Space Grotesk', sans-serif;
}

/* Add any additional global styles if necessary */
</style>