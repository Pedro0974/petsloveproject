<template>
    <footer class="bg-gray-800 text-white p-8 h-[70%] -mt-16">
      <div class="container mx-auto grid grid-cols-1 md:grid-cols-4 gap-4 mb-14">
        <!-- Coluna 1: Logo e Redes Sociais -->
        <div>
          <!-- Sua Logo aqui -->
          <img src="../assets/logo.png" alt="Logo" class="mb-4 w-24">
  
          <!-- Links para Redes Sociais -->
          <div class="flex space-x-4">
            <a href="#" class="text-white hover:text-gray-400">
              <!-- <i class="fab fa-facebook"></i> -->
            </a>
            <a href="#" class="text-white hover:text-gray-400">
              <!-- <i class="fab fa-twitter"></i> -->
            </a>
            <a href="#" class="text-white hover:text-gray-400">
              <!-- <i class="fab fa-instagram"></i> -->
            </a>
          </div>
        </div>
  
        <!-- Coluna 2: Título e Links -->
        <div>
          <h2 class="text-lg font-bold mb-4">Desenvolvedores</h2>
          <ul>
            <li><a href="https://www.instagram.com/pedroo0974/">Pedro Lucas</a></li>
            <li><a href="https://www.instagram.com/victoor_amooriim/">Victor Amorim</a></li>
          </ul>
        </div>
  
        <!-- Coluna 3: Título e Links -->
        <div>
          <h2 class="text-lg font-bold mb-4">Alunos </h2>
          <ul>
            <li><a href="#">Daniel de Sousa</a></li>
            <li><a href="#">Gisele Delfino</a></li>
            <li><a href="#">Jose Antônio Pereira</a></li>
            <li><a href="#">Micaela Chaves</a></li>
            <li><a href="#">Shirley de Souza Rodrigues</a></li>
          </ul>
        </div>
  
        <!-- Coluna 4: Título e Links -->
        <div>
          <h2 class="text-lg font-bold mb-4">Outros</h2>
          <ul>
            <li><a href="#">FAQ</a></li>
            <li><a href="#">Diretrizes</a></li>
            <li><a href="#">Localização</a></li>
            <li><a href="#">Termos e Condições</a></li>
          </ul>
        </div>
      </div>
      <div class="w-full text-center text-xs">
        <label>&copy; 2023  <a href="https://www.instagram.com/victoor_amooriim/" class="underline text-blue-500 font-bold">Victor Amorim</a> & <a href="https://www.instagram.com/pedroo0974/" class="underline text-blue-500 font-bold">Pedro Lucas</a>. Todos os direitos reservados.</label>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    name: 'Footer',
  }
  </script>
  
  <style scoped>
  /* Adicione estilos específicos do componente aqui, se necessário */
  </style>
  