<script setup>
import axios from 'axios';
import { reactive, onMounted } from 'vue';

const params = defineProps(["carrinho", "EliminarItem"]);
console.log(params);

// Usando reactive para o carrinho no Vue
const carrinho = reactive([]);


// Funções para interagir com o carrinho
async function addcarrinho() {
    const resposta_carrinho = await axios.post("http://10.60.44.35:3001/cart/create");
    carrinho.splice(0, carrinho.length, ...resposta_carrinho.data.db); // Atualizando o carrinho
    console.log(carrinho);

}

async function lercarrinho() {
    const resposta_carrinho = await axios.get("http://10.60.44.35:3001/cart/read");  // Método correto para GET
    carrinho.splice(0, carrinho.length, ...resposta_carrinho.data.db); // Atualizando o carrinho
    console.log(carrinho);
}

async function mostracarrinho() {
    const resposta_carrinho = await axios.get("http://10.60.44.35:3001/cart/show"); // Método correto para GET
    carrinho.splice(0, carrinho.length, ...resposta_carrinho.data.db); // Atualizando o carrinho
    console.log(carrinho);
}

// Chama as funções no onMounted para carregar os dados do carrinho ao montar o componente
onMounted(() => {
    addcarrinho();
    mostracarrinho();
    lercarrinho();
});


</script>

<template>
  <div class="sombra">
    <div class="titulo">
      <h1 class="cor">Carrinho:</h1>
    </div>
  </div>

  <div>
    <!-- Botão para redirecionar para a página "monte-sua-festa" -->
    <div class="distancia" v-if="!params.carrinho || params.carrinho.length === 0">
      <a class="persobtn" href="./monte-sua-festa">Ir para Monte sua Festa</a>
      <img class="imagem-carrinho" src="/public/img/carrinho vazio.png" width="150px">
    </div>

    <!-- Lista os itens do carrinho, se não estiver vazio -->
    <div class="item" v-else>
      <Mesa
        v-for="produtoNoCarrinho in params.carrinho"
        :key="produtoNoCarrinho.id"
        :EliminarItem="EliminarItem"
        :produto="produtoNoCarrinho"
        :comprar="true"
      />
      <br />
      
      
    </div>
    
    <div class="btncentro" v-if="params.carrinho && params.carrinho.length > 0">
      <a href="./pagamento"><button class="salvarContinuar">Continuar</button></a>
    </div>
  </div>
</template>

<style scoped>
@import url("~/assets/css/Carrinho_projeto.css");



.display {
  display: flex;
  gap: 15px;
}

.titulo {
  background: #6e32a6;
  color: #f5f5f5;
  text-align: center;
  padding: 0px;
  margin: 0;
  border-radius: 20px;
  font-size: 15px;
  margin-bottom: 20px;
}

.sombra {
  padding: 0px;
  background-color: #f5f5f5;
  border-radius: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.7);
}

.btncentro {
  text-align: center;
  margin-top: auto;
  margin:center;
  margin-right: auto;
}

.btncentro {
    position: fixed;
    bottom: 10px;
    left: calc(50% - 100px);
}

.salvarContinuar {
  background: green;
  cursor: pointer;
  color: #f5f5f5;
  font-size: 15px;
  border-radius: 30px;
}

.salvarContinuar:hover {
  background: lightgreen;
  color: black;
}

.persobtn {
  border: none;
  cursor: pointer;
  transition: background-color 0.5s ease, color 0.5s ease;
  font-size: 20px;
  background-color: #f5f5f5;
  padding: 10px 30px;
  border-radius: 150px;
  text-decoration: none;
  left: 50%;
}

.persobtn:hover {
  background-color: #6e32a6;
  color: white;
}

.distancia {
  margin-left: 42%;
  margin-top: 30px; /* Para garantir que o botão tenha uma distância do topo */
 
}

.imagem-carrinho {
  display: flex;
  margin-top: 60px;
  margin-left: 5%;
}

.cor{
    color:#f5f5f5
}

.item{
  display: flex;
  margin: 10px;
  padding: 10px;
  flex: 0 auto;
  color:#e6e7eb;
  gap:10px;
  border-radius: 15px;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
}



</style>
