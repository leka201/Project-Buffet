<script setup>
import { ref, onMounted } from 'vue';
import { useRouter } from 'vue-router';
import '~/assets/css/perfil.css'; // Importa o CSS externo

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
            <button class="sair" @click="sair">Sair</button> <!-- Botão Sair -->
        </div>
    </div>

    <hr>
    <div class="historico">
        <h3>Últimas compras:</h3>
        <div class="lado_a_lado">
            <img class="imagem" src="https://i0.wp.com/anamariabraga.globo.com/wp-content/uploads/2017/12/coxinha-cremosa.jpg?fit=1200%2C675&ssl=1" width="90" height="90">
            <p>Salgado frito, pequeno, 600 unidades, R$300,00</p>
        </div>
        <!-- Outras compras aqui -->
    </div>
</div>

<!-- Menu -->
<nav class="menu">
    <router-link to="/perfil">{{ menuText }}</router-link>
</nav>
</template>
