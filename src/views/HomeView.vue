<template>
  <div>
    <Carrossel />
    <About />
    <Contacts />
    <Footer />
  </div>
</template>

<script>
import Carrossel from '@/components/Carrossel.vue';
import About from '@/components/About.vue';
import Footer from '@/components/Footer.vue';
import Contacts from '@/components/Contacts.vue'

export default {
  name: 'HomeView',
  components: {
    Carrossel,
    About,
    Footer,
    Contacts
  }
}
</script>
