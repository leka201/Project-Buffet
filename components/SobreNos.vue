<template>
    <section class="sobre" ref="sobreSection">
      <img src="/public/img/Sobre nos.png" alt="Sobre Nós" class="imagem-sobre" />
      <div class="texto-sobre">
        <h2>Sobre Nós</h2>
        <p id="descricao">Aqui vai o texto explicativo sobre a sua empresa.</p>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        lastScrollY: 0, // Armazena a última posição do scroll
        isVisible: false, // Estado de visibilidade
      };
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll);
      this.handleScroll(); // Verifica a visibilidade ao montar
    },
    beforeDestroy() {
      window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
      handleScroll() {
        const currentScrollY = window.scrollY; // Posição atual do scroll
        const sectionPosition = this.$refs.sobreSection.offsetTop; // Posição do topo da seção
        const windowHeight = window.innerHeight;
        const buffer = 50; // Margem para detecção
  
        // Verifica se a seção está visível na viewport
        const isInViewport = sectionPosition < (currentScrollY + windowHeight + buffer) && sectionPosition > (currentScrollY - buffer);
  
        // Aparecer ao descer
        if (currentScrollY > this.lastScrollY && isInViewport) {
          if (!this.isVisible) {
            this.$refs.sobreSection.classList.add('visible'); // Adiciona a classe para aparecer
            this.isVisible = true; // Atualiza o estado de visibilidade
          }
        } 
        // Desaparecer ao subir
        else if (currentScrollY < this.lastScrollY && isInViewport) {
          if (this.isVisible) {
            this.$refs.sobreSection.classList.remove('visible'); // Remove a classe para desaparecer
            this.isVisible = false; // Atualiza o estado de visibilidade
          }
        }
  
        this.lastScrollY = currentScrollY; // Atualiza a última posição do scroll
      },
    },
  }
  </script>
  
  <style scoped>
  .sobre {
    display: flex;
    align-items: center;
    margin: 20px;
    opacity: 0; /* Inicialmente invisível */
    transform: translateY(50px); /* Deslocado para baixo */
    transition: opacity 0.5s ease, transform 0.5s ease; /* Animação */
  }
  
  .sobre.visible {
    opacity: 1; /* Visível quando a classe é adicionada */
    transform: translateY(0); /* Retorna ao lugar */
  }
  
  .imagem-sobre {
    max-width: 600px; /* Largura máxima da imagem */
    margin-right: 20px; /* Espaço entre imagem e texto */
  }
  
  .texto-sobre {
    max-width: 600px; /* Largura máxima do texto */
  }
  </style>
  