<template>
  <div class="background-slider">
    <h1 class="text"> </h1>
  </div>

  <div class="container distanciateoe">
    <div class="header">
      <h1 class="combo-title">Combos de Festa</h1> <!-- Adicionada a classe combo-title -->
    </div>

    <div class="combo-container">
      <div class="combo" v-for="combo in combos" :key="combo.id">
        <div class="combo-content">
          <img :src="combo.image" :alt="combo.title" class="combo-image">
          <div class="overlay">
            <h2>{{ combo.title }}</h2>
            <p>{{ combo.description }}</p>
            <span class="price">Preço: {{ combo.price }}</span>
            <button class="buy-button" @click="redirectTo(combo.link)">Comprar</button>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div>
    <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
    <Rodape />
  </div>
</template>

<script>
export default {
  data() {
    return {
      combos: [
        {
          id: 1,
          title: 'Festa Infantil',
          description: 'Pacote com decoração, bolo e lembrancinhas.',
          image: 'https://rosaazul.cdn.magazord.com.br/img/2022/06/blog/12021/festa-infantil-tema-safari.jpg',
          price: 'R$ 200,00',
          link: '/festainfantil'
        },
        {
          id: 2,
          title: 'Formatura',
          description: 'Pacote com jantar, decoração e fotos.',
          image: 'https://cdn.prod.website-files.com/5fbd45a4128163fe7d9d9b0d/60c791dd48eb58937e0bc659_5.1.jpeg',
          price: 'R$ 1.500,00',
          link: '/formatura'
        },
        {
          id: 3,
          title: 'Festa de 15 Anos',
          description: 'Pacote especial com baile e decoração temática.',
          image: 'https://www.tuacasa.com.br/wp-content/uploads/2019/07/temas-para-festa-de-15-anos-0.jpg',
          price: 'R$ 5.000,00',
          link: '/festaquinze'
        },
        {
          id: 4,
          title: 'Casamento',
          description: 'Pacote completo com buffet, decoração e música.',
          image: 'https://cdn.alboompro.com/5f7e09ac8ef8cb000118b57e_623b314964c1930001437e36/original_size/20-ideias-de-decoracao-para-um-casamento-na-praia-c1f57853d363d37925d6.webp?v=1',
          price: 'R$ 10.000,00',
          link: '/casamento'
        }
      ]
    };
  },
  methods: {
    redirectTo(link) {
      window.location.href = link; // Redireciona para o link especificado
    }
  }
}
</script>

<style scoped>
.header {
  margin-bottom: 20px; /* Espaço entre o título e os combos */
  text-align: center; /* Centraliza o título */
}

.combo-title {
  background-color: #6E32A6; /* Fundo roxo */
  color: white; /* Cor do texto branco */
  padding: 10px 20px; /* Espaçamento interno */
  border-radius: 10px; /* Bordas arredondadas */
  display: inline-block; /* Para o fundo se ajustar ao tamanho do texto */
}

.combo-container {
  display: flex;
  justify-content: center; /* Centraliza os combos horizontalmente */
  flex-wrap: wrap; /* Permite que os combos quebrem para a linha seguinte se não houver espaço */
  gap: 20px; /* Espaçamento entre os combos */
  padding: 0 20px; /* Espaçamento nas bordas */
}

.combo {
  flex: 0 0 15%; /* Define que cada combo ocupará 15% da largura */
  position: relative;
  overflow: hidden; /* Esconde o conteúdo que ultrapassa */
  cursor: pointer;
  border-radius: 10px;
}

.combo-content {
  position: relative;
  transition: transform 0.3s; /* Transição suave para o zoom */
  height: 350px; /* Aumentando a altura do contêiner do combo */
}

.combo:hover .combo-content {
  transform: scale(1.05); /* Efeito de zoom ao passar o mouse */
}

.combo img {
  width: 100%; /* Garante que a imagem preencha toda a largura do combo */
  height: 100%; /* Define a altura da imagem igual à altura do contêiner */
  object-fit: cover; /* Cobre a área da imagem mantendo a proporção */
  border-radius: 10px; /* Bordas arredondadas nas imagens */
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.7); /* Fundo escuro com transparência */
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  opacity: 0; /* Inicialmente invisível */
  transition: opacity 0.3s; /* Transição suave para a opacidade */
}

.combo:hover .overlay {
  opacity: 1; /* Torna visível ao passar o mouse */
}

h2, p, .price {
  margin: 5px 0; /* Margem entre os elementos de texto */
  text-align: center; /* Centraliza o texto */
}

.price {
  font-weight: bold; /* Destaca o preço */
}

.buy-button {
  margin-top: 10px; /* Espaçamento acima do botão */
  padding: 10px 20px; /* Espaçamento interno do botão */
  background-color: #28a745; /* Cor de fundo do botão */
  color: white; /* Cor do texto do botão */
  border: none; /* Remove a borda padrão */
  border-radius: 5px; /* Bordas arredondadas do botão */
  cursor: pointer; /* Muda o cursor ao passar sobre o botão */
  transition: background-color 0.3s; /* Transição suave para a cor de fundo */
}

.buy-button:hover {
  background-color: #218838; /* Cor do botão ao passar o mouse */
}
</style>
