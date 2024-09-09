


<template>
    <div class="cadastro-div">
        <div class="cadastro-div2">
      <h1>Cadastro</h1>
        <form action="login">
        <div class="input-conta">
          <input type="text" id="nome" required>
          <label for="nome">Nome Completo</label>
        </div>
        
        <div class="input-conta">
          <input type="text" id="cpf" required>
          <label for="cpf">CPF</label>
        </div>
        
        <div class="input-conta">
          <input type="email" id="email" required>
          <label for="email">E-mail</label>
        </div>
        
        <div class="input-conta">
          <input type="text" id="cep" required>
          <label for="cep">CEP</label>
        </div>
        
        <div class="input-conta">
          <input type="text" id="endereco" required>
          <label for="endereco">Endereço</label>
        </div>
        
        <div class="input-conta">
          <input type="date" id="data-nascimento" required>
          <label for="data-nascimento">  </label>
        </div>
        
        <div class="input-conta">
          <select id="genero" required>
            <option value="" disabled selected></option>
            <option value="masculino">Masculino</option>
            <option value="feminino">Feminino</option>
            <option value="outro">Outro</option>
          </select>
          <label for="genero">Gênero</label>
        </div>
        
        <div class="input-conta">
          <input type="password" id="senha" minlength="8" required>
          <label for="senha">Crie uma Senha (min. 8 caracteres)</label>
        </div>
        
        <button type="submit">Cadastrar</button>
        <a href="#">Já possui conta? Entrar</a> 
        </form>
        </div>
    </div>

</template>

<style scoped>
@import url("/assets/css/cadastro.css");
</style>