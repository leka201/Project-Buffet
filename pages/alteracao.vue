<template>

    <div class="container">
        <h1>Alterar dados</h1>
        <form>
            <input type="text" readonly placeholder="Nome" minlength="2">
            <input type="text"readonly placeholder="CPF" minlength="8">
            <input type="email" readonly placeholder="E-mail" minlength="2">
            <input type="text" readonly placeholder="Celular" minlength="9">
            <input type="text" readonly placeholder="Endereço" minlength="2">
           

            <!-- Campos de senha -->
            <input type="password" placeholder="Nova Senha" minlength="8">
            <input type="password" placeholder="Confirmar Senha" minlength="8">
            
            <button type="submit" href="perfil">Alterar Dados</button>

        </form>
    </div>

</template>

<style>
@import url("/assets/css/alteracao.css");
</style>