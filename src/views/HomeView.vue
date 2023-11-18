<template>
  <div>
    <Carrossel />
    <About />
    <Footer />
  </div>
</template>

<script>
import Carrossel from '@/components/Carrossel.vue';
import About from '@/components/About.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'HomeView',
  components: {
    Carrossel,
    About,
    Footer
  }
}
</script>
