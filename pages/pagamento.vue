<script setup>

let metodo = ref()
 function alterametodo(valor){
  metodo.value = valor
 }

</script>


<template>
  <div id="app">
     <div class="junto">
      <h1 class="Titulo">Escolha sua forma de pagamento!</h1>

      <form action="./pagamento_aprovado" submit.prevent="confirmPayment" >

        <div class="cartaoSelecionar">
          <p class="cartão" ><strong >Escolha</strong></p>

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
          <input  type="number" v-model="cpfCnpj" minlength="3" required>

          <label class="espaço"> Nome do Cartão:</label>
          <input  type="text" v-model="cardName" minlength="2" required>

          <label for="card-number" class="espaço">Número do Cartão: </label>
          <input v-model="cardNumber" type="text" minlength="2" required>

          <label class="espaço"> Validade:</label>
          <input v-model="expiryDate" placeholder="MM/AA" type="date" required>

          <label class="espaço" for="cvv"> (CVV):</label>
          <input id="cvv" v-model="cvv" type="text" minlength="2" required>

          <label for="installaments">Parcelas:</label>
          <select id="installaments" v-model="installments">
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
        
      <div class="cartaoSelecionar">
        <p href="./carrinho_projeto"><button class="voltar"> Voltar </button></p>
      </div>

      <div v-if="paymentSuccess" >{{ message }}</div>
    </div>
  </div>
</template>

<style scoped>
@import url("~/assets/css/pagamento.css");
</style>