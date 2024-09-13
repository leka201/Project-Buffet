
<template>
     <!-- Pagina de pagamento-->
     <h1 class="Titulo">Escolha sua forma de pagamento!</h1>

     <form action="./pagamento_aprovado.vue">

      <div class="cartaoSelecionar">
        <p class="cartão" ><strong >Escolha o Cartão</strong></p>

        <select >
            <option> Visa </option> 
             <option> Mastercard</option>
             <option> Elo </option>
             <option>Nupay</option>
        </select>

        <p class="pix"><strong>Pix:</strong></p>

        <button>Gerar QRCode</button>
      </div>

       <div>

        <p class="espaço">CPF/CNPJ: </p>
        <input type="text" minlength="3" required>

        <p class="espaço"> Nome do Cartão:</p>
        <input type="text" minlength="2" required>

        <p class="espaço">Número do Cartão: </p>
        <input type="text" minlength="2" required>

        <p class="espaço"> Validade(MM/AAAA):</p>
        <input type="date" required>

        <p class="espaço"> Código(CVV):</p>
        <input  type="text" minlength="2" required>

       </div>

        <div class="cartaoSelecionar">
       <a href="./pagamento_aprovado.vue"> <button class="efetuarPagamento"> Efetuar pagamento</button> </a>
         </div>

   
    </form>
   
    <div class="cartaoSelecionar">
   <a href="./carrinho_projeto.vue"><button class="voltar"> Voltar </button></a>
   </div>
   
    
</template>

<style scoped>
@import url("~/assets/css/pagamento.css");
</style>