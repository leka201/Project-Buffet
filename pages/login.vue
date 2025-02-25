<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router'; // Importa o useRouter
import axios from 'axios';

const params = defineProps(["users"]);
const usuariosTemporarios = reactive([])
const router = useRouter(); // Cria uma instância do router

let email = ref('');
let senha = ref('');

async function puxauser(){

    const response = await axios.get("http://10.60.44.35:3001/user/read")
    usuariosTemporarios.value=response.data.users
    console.log('usuarios')
    console.log(response.data.users)
    }

function autenticar() {
    let user = usuariosTemporarios.value.find(u => u.email === email.value && u.password === senha.value);

    if (!user) {
        alert('Usuário não encontrado');
        return;
    }

    alert('Usuário acessado com sucesso');

    localStorage.setItem("user", JSON.stringify(user));
    router.push('/perfil'); // Redireciona para a página de perfil

}


onMounted(() => {
   puxauser()
})

</script>

<template>
   <form><div class="cadastro-div">
        <div class="cadastro-div2">
            <h1>Login</h1>
            <form @submit.prevent="autenticar">
                <div class="input-conta">
                    <label for="email">Email</label>
                    <input type="email" id="email" name="email" required v-model="email">
                </div>
                <div class="input-conta">
                    <label for="password">Senha</label>
                    <input type="password" id="password" name="password" required v-model="senha">
                </div>
                <button type="submit"href="/perfil" >Entrar</button>
            </form>
            <a href="cadastro">Não tem conta? Crie aqui</a>
        </div>
    </div></form> 
</template>

<style scoped>
@import url("~/assets/css/login.css");
</style>
