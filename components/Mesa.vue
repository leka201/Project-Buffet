<script setup>

const params = defineProps (["produtos", "disponivel", "adicionaAoCarrinho", "comprar", "EliminarItem"]); 


</script>


<template>
    


    <div class="quadrado centerimg">
       
    <h1 class="textoimg">{{params.produtos.nome}} </h1> 


        <img class="redonda " src="/public/img/mesas.png" width="300px" alt="Mesas">

        
        
        <div v-on:click="params.adicionaAoCarrinho(params.produtos)" class="texto" v-if="params.comprar == false || params.comprar == null">Comprar</div>
        <button class="cancelar" v-on:click="params.EliminarItem(params.produtos)" v-if="params.comprar == true">Remover</button>
       
    </div>



</template>

<style scoped>
@import  url("~/assets/css/mesas.css");

</style>