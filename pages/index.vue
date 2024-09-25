<template>
  <div class="background-slider">
    <h1 class="text"> </h1>
  </div>

  <div class="container distanciateoe">
    <!-- Módulo: Cabeçalho -->
    <div class="header">
      <h1>Combos de Festa</h1>
      <br>
    </div>

    <!-- Módulo: Combos -->
    <div class="combo" @click="toggleItems('infantil')">
      <h2>Festa Infantil</h2>
      <div class="items" id="infantil">
        <ul>
          <!-- Itens da Festa Infantil -->
        </ul>
        <div class="combo-card luxe-card">
          <img src="/public/img/Festa infanto.jpg" width="200px">
          <h3>Combo Infantil</h3>
          <p>Inclui: Buffet completo, decoração temática, e DJ ao vivo.</p>
          <span class="price">R$ 3.400</span>
          <div class="button-container">
            <button class="btn">Comprar</button>
          </div>
        </div>
      </div>
    </div>

    <div class="combo" @click="toggleItems('casamento')">
      <h2>Casamento</h2>
      <div class="items" id="casamento">
       
        <div class="combo-card">
           <img src="/public/img/Festa infanto.jpg" width="200px">
          <h3>Combo Casamento </h3>
          <p>Inclui: Buffet gourmet, dj,  open bar. decoração</p>
          <span class="price">R$ 5.500</span>
          <div class="button-container">
            <button class="btn">Comprar</button>
          </div>
        </div>
      </div>
    </div>

    <div class="combo" @click="toggleItems('formatura')">
     
      <h2>Formatura</h2>
      <div class="items" id="formatura">
        <div class="combo-card"> 
          <img src="/public/img/Festa infanto.jpg" width="200px">
          <h3>Combo Fromatura </h3>
          <p>Inclui: Buffet simples e música ambiente.</p>
          <span class="price">R$ 1.500</span>
          <div class="button-container">
            <button class="btn">Comprar</button>
          </div>
        </div>
      </div>
    </div>

    <div class="combo" @click="toggleItems('quinze-anos')">
      <h2>Festa de 15 Anos</h2>
      <div class="items" id="quinze-anos">
        <div class="combo-card">
          <h3>Combo 15 Anos</h3>
          <p>Inclui: Buffet completo, decoração glamourosa e DJ.</p>
          <span class="price">R$ 4.000</span>
          <div class="button-container">
            <button class="btn">Comprar</button>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Módulo: Sobre Nós -->
  <div class="distancia">
    <SobreNos />
  </div>
</template>

<script>
import SobreNos from '~/components/SobreNos.vue';

export default {
  components: {
    SobreNos,
  },
  methods: {
    toggleItems(comboId) {
      const items = document.getElementById(comboId);
      const allItems = document.querySelectorAll('.items');

      allItems.forEach(item => {
        if (item !== items) {
          item.style.display = 'none';
        }
      });

      items.style.display = items.style.display === 'block' ? 'none' : 'block';
    }
  }
}
</script>

<style lang="css" scoped>
body {
  font-family: 'Arial', sans-serif;
  background-color: #f4f4f4;
  margin: 0;
  padding: 20px;
}

.container {
  max-width: 1200px;
  margin: auto;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  background: #f0f0f0; /* Fundo cinza claro */
  display: flex;
  flex-direction: column; /* Organiza em coluna */
  gap: 20px; /* Espaçamento uniforme entre os combos */
}

.header {
  position: relative;
  z-index: 2; /* Fica acima do fundo */
  text-align: center;
  margin-bottom: 20px; /* Espaço entre o título e os combos */
}

.header h1 {
  color: white;
  background: #6E32A6; /* Fundo roxo */
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0 8px 15px rgba(0, 0, 0, 0.3), 0 2px 10px rgba(0, 0, 0, 0.1); /* Sombra elegante */
}

.header::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('caminho-para-sua-imagem-de-arranhado.png') no-repeat center center;
  background-size: cover;
  opacity: 0.2; /* Transparência do arranhado */
  z-index: 1; /* Fica atrás do texto */
}

.combo {
  flex: 1;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 10px;
  cursor: pointer;
  transition: background 0.3s, transform 0.3s;
  background: #e6f0ff; /* Azul neutro e elegante */
  position: relative;
}

.combo:hover {
  background: rgba(200, 200, 200, 0.3);
  transform: translateY(-5px);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2); /* Sombra no hover */
}

.items {
  display: none;
  margin-top: 10px;
}

.items ul {
  list-style-type: none;
  padding: 0;
}

.combo-container {
  margin-top: 10px;
}

.combo-card {
  background: #6E32A6; /* Fundo dos cards */
  color: white;
  border-radius: 8px;
  padding: 15px;
  margin-top: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* Sombra elegante para os cards */
  transition: transform 0.3s;
}

.combo-card:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3); /* Sombra mais intensa no hover */
}

.price {
  font-weight: bold;
  font-size: 1.2em;
}

.button-container {
  margin-top: 10px; /* Espaçamento acima do botão */
}

.btn {
  background: white; /* Fundo branco */
  color: #6E32A6; /* Texto roxo */
  border: 1px solid #6E32A6; /* Borda roxa */
  border-radius: 5px;
  padding: 8px 12px; /* Diminuir tamanho do botão */
  cursor: pointer;
  transition: transform 0.3s; /* Apenas a transformação */
  font-weight: bold;
}

.btn:hover {
  transform: scale(1.05);
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2); /* Sombra no hover do botão */
}

.distanciateoe {
  margin-top: 120px;
}
</style>
