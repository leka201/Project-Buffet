<script setup>
    const params = defineProps (["produto", "adicionaAoCarrinho", "comprar", "EliminarItem"]); 
</script>


<template>
    <div class="quadrado centerimg">
  teste      
        <!--- h1 class="textoimg">{{params.produto.name}} </h1> 
        <img class="redonda " v-bind:src="params.produto.imagem" width="300px" alt="Mesas">
        <div v-on:click="params.adicionaAoCarrinho(params.produto)" class="texto" v-if="params.comprar == false || params.comprar == null">Comprar</div>
        <button class="cancelar" v-on:click="params.EliminarItem(params.produto)" v-if="params.comprar == true">Remover</button -->
    </div>
</template>

<style scoped>
    @import  url("~/assets/css/mesas.css");
</style>