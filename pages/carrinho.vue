
<template>

    <div class="produto">

        <div class="titulo">
            <h1>Carrinho:</h1>
        </div>
        
        <p class="Escritas">Salgado frito, pequeno</p>
        
        <img src="https://i0.wp.com/anamariabraga.globo.com/wp-content/uploads/2017/12/coxinha-cremosa.jpg?fit=1200%2C675&ssl=1" width="300" height="250">
        
    
        <p class="Precos">R$ <span id="preco">50,00</span></p>
    
        <p>Quantidade por cento: <span id="quant.">0</span> </p>
    
        <button class="cancelar">Cancelar</button>
    
        <button onclick='aumentar() '>Adicionar</button>
        <button onclick='diminuir()'>Diminuir</button>

    </div>


    <hr>

    <div class="produto">
    <p class="Escritas">Decoração de festa infantil, do sonic</p>
    
        <img src="https://http2.mlstatic.com/D_NQ_NP_861529-MLB49580616668_042022-O.webp" width="300">
    
    <p class="Precos">R$ 200,00</p>

    <p>Limite: 1</p>
    <button class="cancelar">Cancelar</button>
    </div>

    <hr>

    <div class="produto">
    <p class="Escritas">Conjunto de cadeira e mesa de plástico</p>

        <img src="https://moveislinhares.vteximg.com.br/arquivos/ids/222952-430-430/Conjunto
        -TopPlast-com-Mesas-de-Plastico-Top-e-6-Cadeiras-Valentina-na-cor-Branco---2.jpg" width="300">

    <p class="Precos">R$ 100,00</p>

    <p>Quantidade: <span id="quant.C">0</span></p>

    <button class="cancelar">Cancelar</button>

    <button onclick='maisCadeiras()'>Adicionar</button>
    <button onclick='menosCadeiras()'>Diminuir</button> 
    </div>

    <hr class="carrinho">

    <div class="btncentro">
    <button class="salvarContinuarComprando">Salvar e continuar comprando</button>
    <button class="cancelar">Cancelar tudo</button>
    <a href="./pagamento.vue"><button class="salvarContinuar">continuar</button></a>
    </div>
</template>

<style scoped>
@import url("~/assets/css/Carrinho_projeto.css");
</style>