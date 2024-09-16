<script setup>

const params = defineProps(["produtos"]);

</script>

<template>

    <div class="titulo">
        <h1>Carrinho:</h1>
        
    </div>


    <div class="produto item">
    
    <Mesa v-bind:produtos="produtos[0]" />
    <Mesa v-bind:produtos="produtos[1]" />
    <Mesa v-bind:produtos="produtos[2]" />
    
    <p>Quantidade por cento: <span id="quant.">0</span> </p>

    <button onclick='aumentar() '>Adicionar</button>
    <button onclick='diminuir()'>Diminuir</button>
    <button class="cancelar">Cancelar</button>

</div>

<br/>

<div class="produto item">



<p>Limite: 1</p>
<button class="cancelar">Cancelar</button>
</div>








<hr class="carrinho">

<div class="btncentro">
    <button class="cancelar">Cancelar tudo</button>
    <a href="./pagamento.vue"><button class="salvarContinuar">continuar</button></a>
    </div>
    </template>

<style scoped>

@import url("~/assets/css/Carrinho_projeto.css");

.display{
    display: flex;
    gap:15px;
    justify-content: center;
}

.titulo{
    background: #6E32A6;
    color: #F5F5F5;
    text-align: center;
    padding: 8px;
    margin: 0;
    border-radius: 20px;
    font-size: 15px;
    margin-bottom: 30px ;
}

.btncentro{
    text-align: center;
}

.cancelar{
    background: red;
    cursor: pointer;
    color: #F5F5F5;
    font-size: 15px;
    border-radius: 30px;
}

.cancelar:hover{
    background: lightcoral;
    color: black;
}

.salvarContinuar{
    background: green;
    cursor: pointer;
    color: #F5F5F5;
    font-size: 15px;
    border-radius: 30px;
}

.salvarContinuar:hover{
    background: lightgreen;
    color: black;
}


</style>