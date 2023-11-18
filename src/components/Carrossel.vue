<template>
    <div class="flex h-screen overflow-hidden">
      <!-- Carrossel -->
      <div class="w-full">
        <div
          v-for="(imagem, index) in lista_imagens"
          :key="index"
          :class="{
            'opacity-100': index === imagemAtual,
            'opacity-0': index !== imagemAtual,
            'absolute top-0 left-0 transition-opacity duration-500 ease-in-out': true
          }"
          class="w-full h-[80%] object-cover"
        >
          <img :src="imagem" alt="Imagem" class="w-full h-full object-cover">
          <div class="bg-black/30 absolute w-full h-full top-0"></div>
        </div>
      </div>
  
      <!-- Conteúdo na outra metade da tela -->
      <div class="absolute top-[30%] w-full text-center p-8 flex flex-col items-center justify-center">
        <h1 class="text-4xl font-bold mb-4 text-white">Bem Vindos a Pets Love</h1>
        <p class="text-lg text-white mb-4 ">Nosso amor pelos pets é tão grande que dedicamos todo o nosso trabalho para tornar suas vidas mais felizes e saudáveis</p>
        <button class="bg-blue-500 text-white px-4 py-2 rounded">Agendar Serviço</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Carrossel',
    data() {
      return {
        lista_imagens: [
          require('../assets/cao-esportivo-se-apresentando-durante-a-isca-percorrendo-a-competicao.jpg'),
          require('../assets/gato-brincadeira-petlove.webp'),
          require('../assets/shiba-inu-cachorro-dando-um-passeio.jpg')
        ],
        imagemAtual: 0,
        intervalId: null // Para armazenar o ID do intervalo
      };
    },
    mounted() {
      this.iniciarIntervalo();
    },
    beforeDestroy() {
      clearInterval(this.intervalId); // Limpa o intervalo ao destruir o componente
    },
    methods: {
      proximaImagem() {
        this.imagemAtual = (this.imagemAtual + 1) % this.lista_imagens.length;
      },
      iniciarIntervalo() {
        this.intervalId = setInterval(this.proximaImagem, 5000); // 5000 milissegundos = 5 segundos
      }
    }
  };
  </script>
  
  <style scoped lang="scss">
  /* Estilo adicional para o carrossel, se necessário */
  </style>
  