<template>
  <div>
    <Carrossel />
    <About />
    <Services />
    <Contacts />
    <Footer />
  </div>
</template>

<script>
import Carrossel from '@/components/Carrossel.vue';
import About from '@/components/About.vue';
import Footer from '@/components/Footer.vue';
import Contacts from '@/components/Contacts.vue';
import Services from '@/components/Services.vue';

export default {
  name: 'HomeView',
  components: {
    Carrossel,
    About,
    Footer,
    Contacts,
    Services
  },

  mounted() {
    this.$router.afterEach((to, from) => {
      if (to.hash) {
        const targetElement = document.querySelector(to.hash);
        if (targetElement) {
          targetElement.scrollIntoView({ behavior: 'smooth' });
        }
      } else {
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }
    });
  }
}
</script>
