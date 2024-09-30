<script setup>

    const params = defineProps(["users"])

    let email = ref( '')
    let senha = ref( '')

    function autenticar(){
        let user ={
            name:'',
            cpf:'',
            email:'',
            cep:'',
            endereco:'',
            gender:'',
            born:'',
            password:''
        }

        params.users.map(u=>{
            if (u.email == email.value && u.password==senha.value){
                user = u 
            }
        })

        if(user.name == '' || user.name == null){
            alert('usuarios nao encontrado')
            return
        }

        alert('usuario acessado com sucesso')

        localStorage.setItem("user", JSON.stringify(user))

    }
</script>

<template>

    <div class="cadastro-div">
        <div class="cadastro-div2">
            <h1>Login</h1>
            <form v-on:submit.prevent="autenticar()">
                <div class="input-conta">
                    <label type="email" for="email">Email</label>
                    <input type="email" id="email" name="email" required v-model="email">
                </div>
                <div class="input-conta">
                    <label for="password">Senha</label>
                    <input type="password" id="password" name="password" required v-model="senha">
                </div>
                <button type="submit" href="perfil">Entrar</button>
            </form>
            <a href="cadastro">Não tem conta?crie aqui</a>
           
        </div>
    </div>


</template>


<style scoped>
@import  url("~/assets/css/login.css")
</style>