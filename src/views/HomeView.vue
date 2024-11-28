<template>
  <div class="home">
    <HeroSection />
    <Comparison />
    <FeaturesThree />
    <Features />
    <FeaturesTwo />
    <Contacti />
  </div>
</template>

<script>
import HeroSection from '../components/HeroSection.vue';
import Comparison from '../components/Comparison.vue';
import Features from '../components/Features.vue';
import FeaturesTwo from '../components/FeaturesTwo.vue';
import FeaturesThree from '../components/FeaturesThree.vue';
import Contacti from '../components/Contact.vue';

export default {
  name: 'HomeView',
  components: {
    HeroSection,
    Comparison,
    Features,
    FeaturesTwo,
    FeaturesThree,
    Contacti
  },
};
</script>

<style>
/* Styles specific to the home view */
</style>