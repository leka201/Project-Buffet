<script setup>
import { ref, onMounted } from 'vue';
import { useRouter } from 'vue-router';

let user = ref({});
let compras = ref([]);
const router = useRouter();

function carregarDados() {
    const userData = localStorage.getItem("user");
    if (!userData) return router.push('/login'); 

    try {
        user.value = JSON.parse(userData);
        carregarHistoricoCompras();
    } catch (error) {
        router.push('/login');
    }
}


function carregarHistoricoCompras() {
    compras.value = [
        { id: 1, data: "2025-02-10", descricao: "Buffet de Casamento", valor: 3500.00 },
        { id: 2, data: "2025-01-25", descricao: "Buffet de Aniversário", valor: 1800.00 },
        { id: 3, data: "2024-12-15", descricao: "Buffet Corporativo", valor: 2500.00 }
    ];
}

function sair() {
    localStorage.removeItem("user");
    router.push('/login');
}

// Funções de formatação
const formatarData = (dataISO) => dataISO ? new Date(dataISO).toLocaleDateString("pt-BR") : "Data não disponível";
const formatarCPF = (cpf) => cpf ? cpf.replace(/\D/g, '').replace(/(\d{3})(\d)/g, '$1.').replace(/(\d{3})\.(\d{3})(\d{2})$/, '$1.$2-$3') : "xxx.xxx.xxx-xx";
const formatarMoeda = (valor) => valor ? `R$ ${valor.toFixed(2).replace(".", ",")}` : "Valor não disponível";

onMounted(carregarDados);

</script>

<template>
    <div class="divisao">
        <h1>Meu Perfil</h1>
    </div>

    <div class="informacao" v-if="user.login">
        <div class="inform">
            <div class="img perfil">
                <i class="fa-solid fa-user"></i>
            </div>

            <div class="center meio">
                <h2><strong>{{ user.login }}</strong></h2>
                <hr>
                <h2>Informações Pessoais:</h2>
                <p><strong>Email: </strong>{{ user.email }}</p>
                <p><strong>CPF: </strong>{{ formatarCPF(user.cpf) }}</p>
                <p><strong>Data de nascimento: </strong>{{ formatarData(user.born) }}</p>
            
                <router-link to="/alteracao">
                    <button class="alterar">Alterar</button>
                </router-link>
                <button class="alterar" @click="sair">Sair</button>
            </div>
                
        </div>

        <hr>

        <!-- Informações do Cartão -->
        <div class="informacao-cartao">
            <h2>Informações do Cartão</h2>
            <p><strong>Banco: </strong>{{ user.cartaoBanco || 'Nubank' }}</p>
            <p><strong>Tipo de Cartão: </strong>{{ user.tipoCartao || 'Crédito' }}</p>
            <p><strong>Últimos 4 dígitos: </strong>{{ user.cartao ? user.cartao.slice(-4) : '1135' }}</p>
        </div>

        <hr>

        <div class="historico">
            <h2>Última Compra</h2>
            <div v-if="compras.length">
                <p><strong>Data:</strong> {{ formatarData(compras[0].data) }}</p>
                <p><strong>Descrição:</strong> {{ compras[0].descricao }}</p>
                <p><strong>Valor:</strong> {{ formatarMoeda(compras[0].valor) }}</p>
            </div>
            <p v-else>Nenhuma compra encontrada.</p>

            <h2>Histórico Completo</h2>
            <ul>
                <li v-for="compra in compras" :key="compra.id">
                    {{ formatarData(compra.data) }} - {{ compra.descricao }} - {{ formatarMoeda(compra.valor) }}
                </li>
            </ul>
        </div>
    </div>
</template>



<style scoped>
    @import '~/assets/css/perfil.css';
</style>
