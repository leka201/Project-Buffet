<script setup>
import axios from 'axios';
import Pagamento_aprovado from './pagamento_aprovado.vue';

let metodo = ref()
 function alterametodo(valor){
  metodo.value = valor

}

const pagamento = reactive([])

async function criar (){
  const resposta_pagamento = await axios.post("http://localhost:3000/cart/create")
  pagamento.value = resposta_pagamento.data.db
    console.log(pagamento.value)

    if(pagamento == Pagamento_aprovado){
        alert("pagamento deu bom meu campeão")
    }
    else{
        pagamento != Pagamento_aprovado
        alert("paga a sua fatura meu campeão")
    }

    
  } 

  //lista um unico carrinho indv com pag 
async function mostrapagamento(){
    const resposta_pagamento = await axios.show("http://localhost:3000/cart/show")

    pagamento.value = resposta_pagamento.data.db
    console.log(pagamento.value)
}

// listar todos os carrinhos na tela de perfil
async function lerpagamento(){
    const resposta_pagamento = await axios.read("http://localhost:3000/cart/read")

    pagamento.value = resposta_pagamento.data.db
    console.log(pagamento.value)
}



</script>


<template>
  
     <div class="junto">
      <h1 class="Titulo">Escolha sua forma de pagamento!</h1>

      <form v-on:change="criar()" action="./pagamento_aprovado" class="centro">

        <div class="cartaoSelecionar">

          <label>
            <input type="radio" v-on:change="alterametodo('credit-card')" value="credit-card" name="pagamento">
            Cartão
          </label>

          
          <label>
            <input type="radio" v-on:change="alterametodo('pix')" v-model="paymentMethod" value="pix" name="pagamento">
            PIX
          </label>
        </div>

        <div v-if="metodo == 'credit-card'">
          <label  class="espaço">CPF/CNPJ: </label>
          <input  type="text"  minlength="3" required>

          <label class="espaço"> Nome do Cartão:</label>
          <input  type="text" minlength="2" required>

          <label  class="espaço">Número do Cartão: </label>
          <input  type="text" minlength="2" required>

          <label class="espaço"> Validade:</label>
          <input  placeholder="MM/AA" type="date" required>
          
          <label class="espaço" > (CVV):</label>
          <input  type="text" minlength="2" required>

          <label >Parcelas:</label>
          <select >
            <option value="1">À vista</option>
            <option value="3">3 vezes</option>
            <option value="6">6 vezes</option>
            <option value="12">12 vezes</option>
          </select>
        </div>

        <div class="detalhes" v-if="metodo == 'pix'">
            <p class="pix"><strong>Pix:</strong></p>
            <p>Chave PIX: <strong>SoulFest@gmail.com</strong></p>
            <p>Escaneie o QRcode abaixo:</p>
            <img src="https://png.pngtree.com/png-clipart/20220605/original/pngtree-black-qr-code-for-web-png-image_7964376.png" alt="Código QR PIX" class="pix-qr">
        </div>

        <div class="cartaoSelecionar">
          <p href="./pagamento_aprovado"> <button type="submit" class="efetuarPagamento"> Efetuar pagamento</button> </p>
        </div>

        
        </form>

        
      <div v-if="paymentSuccess" >{{ message }}</div>
    </div>
  
</template>

<style scoped>
@import url("~/assets/css/pagamento.css");
</style>