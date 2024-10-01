<template>
    <div class="cadastro-div">
        <div class="cadastro-div2">
            <h1>Alterar Dados</h1>
            <form @submit.prevent="mostrarMensagem" id="alterar-form">
                <input type="email" id="email" placeholder="Email" required />
                <input type="tel" id="telefone" placeholder="Telefone" required />
                <input type="text" id="endereco" placeholder="Endereço" required />
                <input type="password" id="senha" placeholder="Nova Senha" required />
                <button type="submit">Alterar Dados</button>
            </form>
        </div>
    </div>
</template>

<script setup>
function mostrarMensagem() {
    console.log('Dados alterados');  
}
</script>

<style>
@import url("/assets/css/alteracao.css");
</style>



