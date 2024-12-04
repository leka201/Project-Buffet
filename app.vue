<script setup>

import('./assets/css/Index.css')


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

    { "id": 0, "name": "Decoração de Futebol", "decorations": "decoração_fut","imagem": "https://i.imgur.com/jcg4pBt.png"},
    { "id": 1, "name": "Balões de Futebol", "decorations": "decoração_fut","imagem": "https://i.imgur.com/P1Irwdd.png"},
    { "id": 2, "name": "Painel de Futebol", "decorations": "decoração_fut", "imagem": "https://i.imgur.com/rJfGa7j.png"},
    { "id": 3, "name": "Cestas de Pipas Coloridas", "decorations": "item_mesa", "imagem": "https://i.imgur.com/lpqbjHZ.png"},
    { "id": 4, "name": "Guirlandas de Futebol", "decorations": "decoração_fut", "imagem": "https://i.imgur.com/Vuljog4.png"},

    { "id": 5, "name": "Pipoca em Caixinhas", "food": "comida_salgados", "imagem": "https://i.imgur.com/u6gpKBW.png"},
    { "id": 6, "name": "Mini Hot Dogs", "food": "comida_salgados", "imagem": "https://i.imgur.com/aeE5CkE.png"},
    { "id": 7, "name": "Cupcakes Decorados", "food": "comida_doces","imagem": "https://i.imgur.com/Mi6dD8X.png"},
    { "id": 8, "name": "Biscoitos Decorados", "food": "comida_doces", "imagem": "https://i.imgur.com/47ruFAK.png"},
    { "id": 9, "name": "Suco de Frutas", "food": "comida_bebidas", "imagem": "https://i.imgur.com/29ci6sZ.png"},

    { "id": 10, "name": "Mesa de Princesas", "items": "item_mesas", "imagem": "https://i.imgur.com/YKEVhEw.png"},
    { "id": 11, "name": "Toalha de Mesa Infantil", "items": "item_toalhas", "imagem": "https://i.imgur.com/gKaWKtz.png"},
    { "id": 12, "name": "Pratos e Copos Coloridos", "items": "item_pratos", "imagem": "https://i.imgur.com/eRr2Sys.png"},
    { "id": 13, "name": "Talheres de Plástico", "items": "item_talheres", "imagem": "https://i.imgur.com/XD5A3Bk.png"},
    { "id": 14, "name": "Cadeira Infantil", "items": "item_cadeiras", "imagem": "https://i.imgur.com/FL1NumI.png"},

    { "id": 15, "name": "Arranjo de Flores para 15 Anos", "decorations": "decoração_casam", "imagem": "https://i.imgur.com/3prHXqH.jpeg"},
    { "id": 16, "name": "Painel de LED Personalizado", "decorations": "decoração_casam", "imagem": "https://i.imgur.com/a4eYBE4.jpeg"},
    { "id": 17, "name": "Cortina de Luzes", "decorations": "decoração_casam", "imagem": "https://i.imgur.com/E5PtnwX.png"},
    { "id": 18, "name": "Balcão de Recepção", "decorations": "decoração_casam", "imagem": "https://i.imgur.com/URQ4H9K.png"},
    { "id": 19, "name": "Centro de Mesa com Velas", "decorations": "decoração_casam", "imagem": "https://i.imgur.com/BR9tkKY.png"},

    { "id": 20, "name": "Mini Sanduíches Gourmet", "food": "comida__salgados", "imagem": "https://i.imgur.com/Ll2EXcZ.jpeg"},
   
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
  <Menu></Menu>
  <NuxtPage v-bind:produtos="produtos" v-bind:adicionaAoCarrinho ="adicionaAoCarrinho" v-bind:carrinho="carrinho" v-bind:users="users" v-bind:EliminarItem="EliminarItem"/>

  


</template>
