<script setup>

    const params = defineProps(["users"])

    const user = reactive({
        name:'',
        cpf:'',
        email:'',
        cep:'',
        endereco:'',
        gender:'',
        born:'',
        password:''

    }) 

    function enviaforms(){
        params.users.push(user)
        alert('usuario cadastrado com  sucesso')
        console.log(params.users)
    }

</script>


<template>
   

    <div class="cadastro-div">
        <div class="cadastro-div2">
            <h1>Cadastro</h1>
            <form v-on:submit.prevent="enviaforms()">
                <div class="input-conta">
                    <label for="nome">Nome Completo</label>
                    <input type="text" id="nome" minlength="2" required v-model="user.name">
                </div>
                
                <div class="input-conta">
                    <label for="cpf">CPF</label>
                    <input type="text" id="cpf" minlength="8" required v-model="user.cpf">
                </div>
                
                <div class="input-conta">
                    <label for="email">Email</label>
                    <input type="email" id="email" required v-model="user.email">
                </div>
                
                <div class="input-conta">
                    <label for="cep">CEP</label>
                    <input type="text" id="cep"minlength="9" required v-model="user.cep">
                </div>
                
                <div class="input-conta">
                    <label for="endereco">Endereço</label>
                    <input type="text" id="endereco" minlength="2" required v-model="user.endereco">
                </div>
                
                <div class="input-conta">
                    <label for="data-nascimento">Data de Nascimento</label>
                    <input type="date" id="data-nascimento" required v-model="user.born">
                </div>
                
                <div class="input-conta">
                    <label for="genero">Gênero</label>
                    <select id="genero" required v-model="user.gender">
                        <option value="" disabled selected></option>
                        <option value="masculino">Masculino</option>
                        <option value="feminino">Feminino</option>
                        <option value="outro">Outro</option>
                    </select>
                </div>
                
                <div class="input-conta">
                    <label for="senha">Crie uma Senha (min. 8 caracteres)</label>
                    <input type="password" id="senha" minlength="8" required v-model="user.password">
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