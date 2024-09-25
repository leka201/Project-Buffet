<script setup>

const params = defineProps (["produtos", "disponivel", "adicionaAoCarrinho"]); 

</script>


<template>
    


    <div class="quadrado centerimg">
       
    <h1 class="textoimg">{{params.produtos.nome}} </h1> 


        <img class="redonda " src="/public/img/mesas.png" width="300px" alt="Mesas">

        
        
        <div v-on:click="params.adicionaAoCarrinho(params.produtos)" class="texto" v-if="comprar==false">Comprar </div>

       
    </div>



</template>

<style scoped>
@import  url("~/assets/css/mesas.css");

</style>