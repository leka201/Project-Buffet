<script setup>

import axios from 'axios';

const params = defineProps(["carrinho", "EliminarItem"]);
console.log(params)
const carrinho = reactive([])

async function addcarrinho(){
    const resposta_carrinho = await axios.post("http://localhost:3001/cart/create")

    carrinho.value = resposta_carrinho.data.db
    console.log(carrinho.value)
}

async function lercarrinho(){
    const resposta_carrinho = await axios.read("http://localhost:3001/cart/read")

    carrinho.value = resposta_carrinho.data.db
    console.log(carrinho.value)
}

async function mostracarrinho(){
    const resposta_carrinho = await axios.show("http://localhost:3001/cart/show")

    carrinho.value = resposta_carrinho.data.db
    console.log(carrinho.value)
}




onMounted(() => {
    addcarrinho()
    mostracarrinho()
    lercarrinho()
    
    
})

</script>

<template>

<div class="sombra">
    <div class="titulo">
        <h1>Carrinho:</h1>
    </div>
</div>


<div class=" item">
    <Mesa v-bind:EliminarItem="EliminarItem" v-for="produtoNoCarrinho in params.carrinho" v-bind:produto="produtoNoCarrinho" v-bind:comprar="true" />
</div> 


<br/>

<hr class="carrinho">

<div class="btncentro">
    <!-- <button class="cancelar">Cancelar tudo</button> -->
    <a href="./pagamento"><button class="salvarContinuar">continuar</button></a>
    </div>
    </template>

<style scoped>

@import url("~/assets/css/Carrinho_projeto.css");

.display{
    display: flex;
    gap:15px;
}

.titulo{
    background: #6E32A6;
    color: #F5F5F5;
    text-align: center;
    padding: 0px;
    margin: 0;
    border-radius: 20px;
    font-size: 15px;
    margin-bottom: 20px ;
}
.sombra{
    padding: 0px;
    background-color: #f8f8f8;
    border-radius: 20px; /* Bordas arredondadas (opcional) */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.7); /* Horizontal, vertical, desfoque, cor */
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