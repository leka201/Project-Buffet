<template>
     <!-- Pagina de pagamento-->
     <h1 class="Titulo">Escolha sua forma de pagamento!</h1>

     <form action="./pagamento_aprovado.html">

        <p class="cartão" ><strong >Escolha o Cartão</strong></p>

        <select >
            <option> Visa </option> 
             <option> Mastercard</option>
             <option> Elo </option>
             <option>Nupay</option>
        </select>

        <p class="pix"><strong>Pix:</strong></p>

        <button>Gerar QRCode</button>

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

        
    
       <a href="./revisao.html"> <button class="efetuarPagamento"> Efetuar pagamento</button> </a>

   
    </form>
   
   <a href="./carrinho_projeto.html"><button class="voltar"> Voltar </button></a>
    
</template>