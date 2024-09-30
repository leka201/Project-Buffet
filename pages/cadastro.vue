


<template>
   

    <div class="cadastro-div">
        <div class="cadastro-div2">
            <h1>Cadastro</h1>
            <form action="login">
                <div class="input-conta">
                    <label for="nome">Nome Completo</label>
                    <input type="text" id="nome" minlength="2" required>
                </div>
                
                <div class="input-conta">
                    <label for="cpf">CPF</label>
                    <input type="text" id="cpf" minlength="8" required>
                </div>
                
                <div class="input-conta">
                    <label for="email">Email</label>
                    <input type="email" id="email" required>
                </div>
                
                <div class="input-conta">
                    <label for="cep">CEP</label>
                    <input type="text" id="cep"minlength="9" required>
                </div>
                
                <div class="input-conta">
                    <label for="endereco">Endereço</label>
                    <input type="text" id="endereco" minlength="2" required>
                </div>
                
                <div class="input-conta">
                    <label for="data-nascimento">Data de Nascimento</label>
                    <input type="date" id="data-nascimento" required>
                </div>
                
                <div class="input-conta">
                    <label for="genero">Gênero</label>
                    <select id="genero" required>
                        <option value="" disabled selected></option>
                        <option value="masculino">Masculino</option>
                        <option value="feminino">Feminino</option>
                        <option value="outro">Outro</option>
                    </select>
                </div>
                
                <div class="input-conta">
                    <label for="senha">Crie uma Senha (min. 8 caracteres)</label>
                    <input type="password" id="senha" minlength="8" required>
                </div>
                
                <button type="submit">Cadastrar</button>
                <a href="login">Já possui conta? Entrar</a> 
            </form>
        </div>
    </div>



</template>

<style scoped>
@import url("/assets/css/cadastro.css");
</style>