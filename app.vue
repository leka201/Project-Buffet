<script setup>

import('~/assets/css/index.css')


const users = reactive([
    {
        name: 'Ana Silva',
        cpf: '123.456.789-00',
        email: 'ana@example.com',
        cep: '12345-678',
        endereco: 'Rua A, 123',
        gender: 'Feminino',
        born: '1990-01-01',
        password: '123'
    },
    {
        name: 'Carlos Souza',
        cpf: '987.654.321-00',
        email: 'carlos@example.com',
        cep: '87654-321',
        endereco: 'Avenida B, 456',
        gender: 'Masculino',
        born: '1985-05-15',
        password: '123'
    },
    {
        name: 'Fernanda Lima',
        cpf: '321.654.987-00',
        email: 'fernanda@example.com',
        cep: '34567-890',
        endereco: 'Praça C, 789',
        gender: 'Feminino',
        born: '1992-03-20',
        password: '123'
    },
    {
        name: 'João Oliveira',
        cpf: '654.321.987-00',
        email: 'joao@example.com',
        cep: '56789-012',
        endereco: 'Rua D, 101',
        gender: 'Masculino',
        born: '1988-07-30',
        password: '123'
    },
    {
        name: 'Mariana Costa',
        cpf: '789.123.456-00',
        email: 'mariana@example.com',
        cep: '21098-765',
        endereco: 'Avenida E, 202',
        gender: 'Feminino',
        born: '1995-11-11',
        password: '123'
    }
]);

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
  <NuxtPage v-bind:produtos="produtos" v-bind:adicionaAoCarrinho ="adicionaAoCarrinho" v-bind:users="users"/>

  


</template>
