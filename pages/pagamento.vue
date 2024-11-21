<script setup>
import { ref, reactive } from 'vue';
import axios from 'axios';
import Pagamento_aprovado from './pagamento_aprovado.vue';
import QRCode from 'qrcode.vue'; // Importando a biblioteca de QR Code

let metodo = ref();
let paymentMethod = ref(''); // Variável para o método de pagamento
let pagamento = reactive([]);
let qrCodeValue = ref(''); // Valor que será codificado no QR Code

function alterametodo(valor) {
    metodo.value = valor;
}

async function criar() {
    const resposta_pagamento = await axios.post("http://localhost:3000/cart/create");
    pagamento.value = resposta_pagamento.data.db;
    console.log(pagamento.value);

    if (pagamento == Pagamento_aprovado) {
        alert("Pagamento deu bom, meu campeão");
    } else {
        pagamento != Pagamento_aprovado;
        alert("Paga a sua fatura, meu campeão");
    }

    // Gerar um novo valor aleatório para o QR Code
    if (metodo.value === 'pix') {
        qrCodeValue.value = `Chave PIX: SoulFest@gmail.com?${Math.random()}`; // Valor dinâmico para o QR Code
    }
}

// Lista um único carrinho indv com pagamento
async function mostrapagamento() {
    const resposta_pagamento = await axios.get("http://localhost:3000/cart/show");
    pagamento.value = resposta_pagamento.data.db;
    console.log(pagamento.value);
}

// Listar todos os carrinhos na tela de perfil
async function lerpagamento() {
    const resposta_pagamento = await axios.get("http://localhost:3000/cart/read");
    pagamento.value = resposta_pagamento.data.db;
    console.log(pagamento.value);
}
</script>

<template>
    <div class="junto">
        <h1 class="Titulo">Escolha sua forma de pagamento!</h1>

        <form v-on:change="criar()" action="./pagamento_aprovado" class="centro">

            <div class="cartaoSelecionar">
                <label>
                    <input type="radio" v-on:change="alterametodo('credit-card')" value="credit-card" name="pagamento">
                    Cartão
                </label>

                <label>
                    <input type="radio" v-on:change="alterametodo('pix')" v-model="paymentMethod" value="pix" name="pagamento">
                    PIX
                </label>
            </div>

            <div v-if="metodo == 'credit-card'">
                <label class="espaço">CPF/CNPJ: </label>
                <input type="text" minlength="3" required>

                <label class="espaço">Nome do Cartão:</label>
                <input type="text" minlength="2" required>

                <label class="espaço">Número do Cartão: </label>
                <input type="text" minlength="2" required>

                <label class="espaço">Validade:</label>
                <input placeholder="MM/AA" type="date" required>

                <label class="espaço">(CVV):</label>
                <input type="text" minlength="2" required>

                <label>Parcelas:</label>
                <select>
                    <option value="1">À vista</option>
                    <option value="3">3 vezes</option>
                    <option value="6">6 vezes</option>
                    <option value="12">12 vezes</option>
                </select>
            </div>

            <div class="detalhes" v-if="metodo == 'pix'">
                <p class="pix"><strong>Pix:</strong></p>
                <p>Chave PIX: <strong>SoulFest@gmail.com</strong></p>
                <p>Escaneie o QR Code abaixo:</p>
                <QRCode :value="qrCodeValue" :size="200" /> <!-- Adicionando o QR Code -->
            </div>

            <div class="cartaoSelecionar">
                <button type="submit" class="efetuarPagamento">Efetuar pagamento</button>
            </div>
        </form>

        <div v-if="paymentSuccess">{{ message }}</div>
    </div>
</template>

<style scoped>
@import url("~/assets/css/pagamento.css");
</style>
