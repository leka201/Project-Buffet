<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router'; // Importa o useRouter

const params = defineProps(["users"]);

let email = ref('');
let senha = ref('');
const router = useRouter(); // Cria uma instância do router

// Usuários temporários para validação
const usuariosTemporarios = [
    { name: 'João', cpf: '12345678900', email: 'joao@example.com', cep: '12345-678', endereco: 'Rua A, 123', gender: 'Masculino', born: '1990-01-01', password: 'senha123' },
    { name: 'Maria', cpf: '98765432100', email: 'maria@example.com', cep: '87654-321', endereco: 'Rua B, 456', gender: 'Feminino', born: '1992-02-02', password: 'senha456' }
];

function autenticar() {
    let user = usuariosTemporarios.find(u => u.email === email.value && u.password === senha.value);

    if (!user) {
        alert('Usuário não encontrado');
        return;
    }

    alert('Usuário acessado com sucesso');
    localStorage.setItem("user", JSON.stringify(user));
    router.push('/perfil'); // Redireciona para a página de perfil
}
</script>

<template>
    <div class="cadastro-div">
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
                <button type="submit">Entrar</button>
            </form>
            <a href="cadastro">Não tem conta? Crie aqui</a>
        </div>
    </div>
</template>

<style scoped>
@import url("~/assets/css/login.css");
</style>
