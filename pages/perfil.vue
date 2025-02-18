<script setup>
import { ref, onMounted } from 'vue';
import { useRouter } from 'vue-router';

let user = ref({});
let compras = ref([]);
let mostrarcpf = ref(false)
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

function toggleMostrarCpf() {
    mostrarcpf.value = !mostrarcpf.value;
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
                <p v-if="mostrarcpf"><strong>CPF: </strong>{{ formatarCPF(user.cpf) }}</p>
                <p v-else><strong>CPF: </strong>xxx.xxx.xxx-xx</p>
                <button
                    @click="toggleMostrarCpf"
                    class="p-2 bg-gray-200 rounded hover:bg-gray-300 transition"
                    >
                    <span v-if="mostrarcpf">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M12 9c2.21 0 4 1.79 4 4s-1.79 4-4 4-4-1.79-4-4 1.79-4 4-4z"/>
                        <path stroke-linecap="round" stroke-linejoin="round" d="M2.458 12C3.732 7.943 7.761 5 12 5c4.24 0 8.268 2.943 9.542 7-1.274 4.057-5.303 7-9.542 7-4.24 0-8.268-2.943-9.542-7z"/>
                        </svg>
                    </span>
                    <span v-else>
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M13.875 18.825c-.624.033-1.258.05-1.875.05-4.24 0-8.268-2.943-9.542-7C3.732 7.943 7.761 5 12 5c.618 0 1.251.017 1.875.05M21 21l-5.197-5.197m0 0A9.935 9.935 0 0112 17c-4.24 0-8.268-2.943-9.542-7C3.732 7.943 7.761 5 12 5c4.239 0 8.268 2.943 9.542 7-.544 1.743-1.5 3.278-2.697 4.497zm0 0L21 21z"/>
                        </svg>
                    </span>
                </button>                
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
