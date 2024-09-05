<template>
    <div class="container">
        <h2>Recuperar Senha</h2>
        <form class="reset-form">
            <label for="cpf">Digite seu CPF:</label>
            <input type="text" id="cpf" name="cpf" required placeholder="000.000.000-00" pattern="\d{3}\.\d{3}\.\d{3}-\d{2}" title="Digite o CPF no formato: 000.000.000-00">

            <label for="email">Digite seu e-mail:</label>
            <input type="email" id="email" name="email" required placeholder="exemplo@dominio.com">

            <label for="phone">Digite seu número de telefone:</label>
            <input type="tel" id="phone" name="phone" placeholder="(00) 00000-0000" pattern="\(\d{2}\) \d{4,5}-\d{4}" title="Digite o telefone no formato: (00) 00000-0000">

            <button type="submit">Enviar</button>
        </form>
        <a href="#" class="back-link">Voltar para o login</a>
    </div>
</template>