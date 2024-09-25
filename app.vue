<script setup>

import('~/assets/css/index.css')

const produtos = reactive([
{
        id:0,
        nome: "Decoração de Futebol",
        preco: "R$50,00",
        disponivel: false, 
    },
    {
        id:1,
        nome: "Cadeiras e Mesas",
        preço: "R$100,00",
        disponivel: false,
    },
    {
        id:2,
        nome: "salgados",
        preco:"R$50,00",
        disponivel:false,
    },
    {
        id:3,
        nome: "refrigerantes",
        preco: "R$50,00",
        disponivel: false,
    },
    {
        id:4,
        nome:"bolos",
        preço: "R$150,00",
        disponivel: false,
    },
])

function adicionaAoCarrinho( produto ){
    produtos.push(produto)
}

</script>


<template>
  


    <Head>        <Script src="./assets/js/font-awesome-v6.6.js"></Script>    </Head>
  <Menu/>
  <NuxtPage v-bind:produtos="produtos" v-bind:adicionaAoCarrinho ="adicionaAoCarrinho"/>
  


</template>
