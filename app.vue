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

    { "id": 0, "nome": "Decoração de Futebol", "preco": "R$50,00", "tipo": "Decoração", "dimensão": "M", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/jcg4pBt.png"},
    { "id": 1, "nome": "Balões de Futebol", "preco": "R$30,00", "tipo": "Decoração", "dimensão": "M", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/P1Irwdd.png"},
    { "id": 2, "nome": "Painel de Futebol", "preco": "R$100,00", "tipo": "Decoração", "dimensão": "L", "alugado": true, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/rJfGa7j.png"},
    { "id": 3, "nome": "Cestas de Pipas Coloridas", "preco": "R$40,00", "tipo": "Decoração", "dimensão": "M", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/lpqbjHZ.png"},
    { "id": 4, "nome": "Guirlandas de Futebol", "preco": "R$25,00", "tipo": "Decoração", "dimensão": "P", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/Vuljog4.png"},

    { "id": 5, "nome": "Pipoca em Caixinhas", "preco": "R$20,00", "tipo": "Comida", "dimensão": "P", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/u6gpKBW.png"},
    { "id": 6, "nome": "Mini Hot Dogs", "preco": "R$40,00", "tipo": "Comida", "dimensão": "M", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/aeE5CkE.png"},
    { "id": 7, "nome": "Cupcakes Decorados", "preco": "R$60,00", "tipo": "Comida", "dimensão": "M", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/Mi6dD8X.png"},
    { "id": 8, "nome": "Biscoitos Decorados", "preco": "R$35,00", "tipo": "Comida", "dimensão": "P", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/47ruFAK.png"},
    { "id": 9, "nome": "Suco de Frutas", "preco": "R$25,00", "tipo": "Comida", "dimensão": "M", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/29ci6sZ.png"},

    { "id": 10, "nome": "Mesa de Princesas", "preco": "R$80,00", "tipo": "Mesa", "dimensão": "M", "alugado": true, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/YKEVhEw.png"},
    { "id": 11, "nome": "Toalha de Mesa Infantil", "preco": "R$20,00", "tipo": "Mesa", "dimensão": "M", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/gKaWKtz.png"},
    { "id": 12, "nome": "Pratos e Copos Coloridos", "preco": "R$15,00", "tipo": "Mesa", "dimensão": "P", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/eRr2Sys.png"},
    { "id": 13, "nome": "Talheres de Plástico", "preco": "R$10,00", "tipo": "Mesa", "dimensão": "P", "alugado": false, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/XD5A3Bk.png"},
    { "id": 14, "nome": "Cadeira Infantil", "preco": "R$25,00", "tipo": "Mesa", "dimensão": "P", "alugado": true, "ocasião": "Festa Infantil" , "imagem": "https://i.imgur.com/FL1NumI.png"},

    { "id": 15, "nome": "Arranjo de Flores para 15 Anos", "preco": "R$120,00", "tipo": "Decoração", "dimensão": "L", "alugado": false, "ocasião": "15 Anos" , "imagem": "https://i.imgur.com/3prHXqH.jpeg"},
    { "id": 16, "nome": "Painel de LED Personalizado", "preco": "R$200,00", "tipo": "Decoração", "dimensão": "L", "alugado": true, "ocasião": "15 Anos" , "imagem": "https://i.imgur.com/a4eYBE4.jpeg"},
    { "id": 17, "nome": "Cortina de Luzes", "preco": "R$80,00", "tipo": "Decoração", "dimensão": "M", "alugado": true, "ocasião": "15 Anos" , "imagem": "https://i.imgur.com/E5PtnwX.png"},
    { "id": 18, "nome": "Balcão de Recepção", "preco": "R$150,00", "tipo": "Decoração", "dimensão": "L", "alugado": true, "ocasião": "15 Anos" , "imagem": "https://i.imgur.com/URQ4H9K.png"},
    { "id": 19, "nome": "Centro de Mesa com Velas", "preco": "R$50,00", "tipo": "Decoração", "dimensão": "P", "alugado": false, "ocasião": "15 Anos" , "imagem": "https://i.imgur.com/BR9tkKY.png"},

    { "id": 20, "nome": "Mini Sanduíches Gourmet", "preco": "R$70,00", "tipo": "Comida", "dimensão": "M", "alugado": false, "ocasião": "15 Anos" , "imagem": "https://i.imgur.com/Ll2EXcZ.jpeg"},
   
])

function adicionaAoCarrinho( produto ){
    carrinho.push(produto)
    alert("Produto adicionado com sucesso")
}

function EliminarItem(produto){
    carrinho.forEach((c,index)=>{
        console.log(c.id, produto.id)
        if(c.id==produto.id){
            carrinho.splice(index, 1)
        }
    })
}

const carrinho = reactive ([

])

</script>


<template>
  


    <Head>        <Script src="./assets/js/font-awesome-v6.6.js"></Script>    </Head>
  <Menu/>
  <NuxtPage v-bind:produtos="produtos" v-bind:adicionaAoCarrinho ="adicionaAoCarrinho" v-bind:carrinho="carrinho" v-bind:users="users" v-bind:EliminarItem="EliminarItem"/>

  


</template>
