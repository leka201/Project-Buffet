<script setup>
import { ref, watch, onMounted } from 'vue';

let linkSelecionado = ref('inicio');
let usuarioLogado = ref(false); // Inicializa como não logado

// Função para alterar o link selecionado
function alteraLinkSelecionado(valor) {
    linkSelecionado.value = valor;
}

// Função para verificar se o usuário está logado
function verificarLogin() {
    if (process.client) { // Verifica se está no lado do cliente
        usuarioLogado.value = !!localStorage.getItem("user"); // Atualiza o estado de login
    }
}

// Executa a verificação quando o componente é montado
onMounted(() => {
    verificarLogin();
});

// Observa mudanças no localStorage para atualizar o estado de login
watch(() => localStorage.getItem("user"), (newValue) => {
    usuarioLogado.value = !!newValue; // Atualiza o estado de login
});
</script>

<template>
<div class="bordaredonda">
    <span class="fundoroxo">
        <i class="fa-solid fa-location-dot distpalavras"></i>
        <span class="dist1"> R. Episcopal, 700 - Centro, São Carlos - SP, 13560-570 </span>
        <i class="fa-solid fa-phone dist2"></i>
        <span class="dist1"> +55 16 992448042 </span>
        <i class="fa-solid fa-envelope dist2"></i>
        <span class="dist1"> soulfest@gmail.com</span>
    </span>
</div>

<div class="letraroxa fundobranco menu">
    <h1 class="logo">
        <font-awesome-icon :icon="['fas', 'envelope']" />
        <img class="margin2" src="/public/img/Logo soul fest.png" width="120px">
    </h1>
    <div></div>
    <div>
        <NuxtLink v-bind:class="['margin', 'persobtn', linkSelecionado == 'inicio' ? 'ativo' : '']" to="/" v-on:click="alteraLinkSelecionado('inicio')"> Página inicial </NuxtLink>
        <NuxtLink v-bind:class="['margin', 'persobtn', linkSelecionado == 'mesas' ? 'ativo' : '']" to="/monte-sua-festa" v-on:click="alteraLinkSelecionado('mesas')"> Monte Sua festa </NuxtLink>
        <NuxtLink v-bind:class="['margin', 'persobtn', linkSelecionado == 'Carrinho' ? 'ativo' : '']" to="/carrinho" v-on:click="alteraLinkSelecionado('Carrinho')"> Carrinho </NuxtLink>
        <NuxtLink v-bind:class="['margin', 'persobtn', linkSelecionado == 'perfil' ? 'ativo' : '']" to="/perfil" v-on:click="alteraLinkSelecionado('perfil')"> {{ usuarioLogado ? 'Perfil' : 'Login' }} </NuxtLink>
    </div>
</div>








    
</template>

<style scoped>
/* Adicione seu estilo aqui */
</style>
