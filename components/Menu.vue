<script setup>






let linkSelecionado = ref('inicio')

function alteraLinkSelecionado(valor) {
    linkSelecionado.value = valor
}


</script>



<template>

<div class="bordaredonda">

<span class="fundoroxo "> <i class="fa-solid fa-location-dot distpalavras ">   </i> <spam class="dist1">R. Episcopal, 700 - Centro, São Carlos - SP, 13560-570   </spam>   
    
                         <i class="fa-solid fa-phone dist2 "></i> <span class="dist1"> +55 16 992448042 </span>
                         <i class="fa-solid fa-envelope dist2"></i> <span class="dist1"> mateusbahia@gmail.com</span> 
          
                        </span>  
</div>

<div class="letraroxa fundobranco menu">


        <h1>    <font-awesome-icon :icon="['fas', 'envelope']" /> Jorges Buffet </h1>
        <div>
            <NuxtLink v-bind:class="['margin ','persobtn' , linkSelecionado == 'inicio'?'ativo':'']" to="/" v-on:click="alteraLinkSelecionado('inicio')"> Pagina inicial   </NuxtLink>
            <NuxtLink v-bind:class="['margin ','persobtn' , linkSelecionado == 'mesas'?'ativo':'']" to="/mesas" v-on:click="alteraLinkSelecionado('mesas')">  Mesas   </NuxtLink>
            <NuxtLink v-bind:class="['margin ','persobtn' , linkSelecionado == 'decorações'?'ativo':'']" to="/decoracoes" v-on:click="alteraLinkSelecionado('decorações')">  Decorações  </NuxtLink>
            <NuxtLink v-bind:class="['margin ','persobtn' , linkSelecionado == 'comidas'?'ativo':'']" to="/comidas" v-on:click="alteraLinkSelecionado('comidas')"> Comidas   </NuxtLink>
            <NuxtLink v-bind:class="['margin ','persobtn' , linkSelecionado == 'Carrinho'?'ativo':'']" to="/carrinho" v-on:click="alteraLinkSelecionado('Carrinho')">  Carrinho  </NuxtLink> 
            <NuxtLink v-bind:class="['margin ','persobtn' , linkSelecionado == 'login'?'ativo':'']" to="/login" v-on:click="alteraLinkSelecionado('login')">  Login   </NuxtLink>
        </div>

</div>

</template>

<style  scoped>


</style>