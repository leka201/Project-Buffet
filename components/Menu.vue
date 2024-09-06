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

<div class="letraroxa fundobranco">


<h1>
    <strong>
        EarlyBird   <NuxtLink v-bind:class="['margin ' , linkSelecionado == 'inicio'?'ativo':'']" to="/" v-on:click="alteraLinkSelecionado('inicio')"><button  class="persobtn">  Pagina inicial  </button> </NuxtLink>
                    <NuxtLink class="margin marginbtn" to="/" v-on:click="alteraLinkSelecionado('mesas')"><button  class="persobtn">  Mesas  </button> </NuxtLink>
                    <NuxtLink class="margin marginbtn" to="/decorações"><button  class="persobtn">  Decorações  </button> </NuxtLink>
                    <NuxtLink class="margin marginbtn" to="futuro index.html"><button  class="persobtn">  Comidas  </button> </NuxtLink>
                    <NuxtLink class="margin marginbtn " to="futuro index.html"><button  class="persobtn">  Doces  </button> </NuxtLink>
                    <NuxtLink class="margin marginbtn " to="/login"><button  class="persobtn">  Login  </button> </NuxtLink>
    </strong>
</h1>

</div>

</template>

<style  scoped>

.ativo{

    
}

</style>