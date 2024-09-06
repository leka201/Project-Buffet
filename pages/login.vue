

<template>
    <div class="login-div">
    <div class="login-div2">
      <h1>Login</h1>
      <form action="index">


        <div class="input-conta">
          <input type="email"  required>
          <label>E-mail</label>
        </div>
        <div class="input-conta">
          <input type="password" required>
          <label>Senha</label>
        </div>
        <button type="submit" a target="_blank" href="index.vue">Entrar</button>
        
        <a target="_blank" href="cadastro.vue">Criar uma conta</a>
      </form>
    </div>
  </div>
</template>

<style scoped>
@import  url("~/assets/css/login.css");
</style>