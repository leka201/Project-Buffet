<script setup>
import { ref, onMounted } from 'vue';
import { useRouter } from 'vue-router';
import axios from 'axios'; 


let user = ref({});
let menuText = ref('Perfil'); // Variável reativa para o texto do menu
const router = useRouter();

function carregadados() {
    const userData = localStorage.getItem("user");
    if (userData) {
        try {
            user.value = JSON.parse(userData);
            } catch (error) {
                console.error("Erro ao parsear dados do usuário:", error);
                router.push('/login'); // Redireciona se houver erro
                }
                } else {
        router.push('/login'); // Redireciona se não houver usuário
    }
}

function sair() {
    localStorage.removeItem("user"); // Remove o usuário do localStorage
    menuText.value = 'Login'; // Muda o texto do menu
    router.push('/login'); // Redireciona para a tela de login
}






onMounted(() => {
    carregadados();

});
</script>

<template>
<div class="divisao">
    <h1>Meu Perfil</h1>
</div>

<div class="informacao" v-if="user.name">
    <div class="inform">
        <div class="img perfil">
            <i class="fa-solid fa-user"></i>
        </div>

        <div class="center meio">
            <h2><strong>{{ user.name }}</strong></h2>
            <hr>
            <h2>Informações Pessoais:</h2>
            <p><strong>E-mail: </strong>{{ user.email }}</p>
            <p><strong>Data de nascimento: </strong>{{ user.born }}</p>
            <p><strong>Endereço: </strong>{{ user.endereco }}</p>
            <p><strong>Cartão: </strong>nupay</p>
            <router-link to="/alteracao">
                <button class="alterar">Alterar</button>
            </router-link>
            <button class="alterar" @click="sair">Sair</button> <!-- Botão Sair -->
        </div>
    </div>

    <hr>
    <div class="historico">
        
        <h2 v-on="mostrapagamento">
            Ultima compra sua 
        </h2>

        <h2 v-on="mostrapagamento">
           Seu historico inteiro 
        </h2>
        <!-- Outras compras aqui -->
    </div>
</div>


</template>

<style scoped>
    @import '~/assets/css/perfil.css';
</style>