<script setup>

    import ('~/assets/css/monte-sua-festa.css')
    import ('~/assets/css/animate.min.css')
    import axios from 'axios';

    const params = defineProps(["adicionaAoCarrinho"])
    
    const produtos = ref([])
    async function BuscarProdutos(){

        const resposta = await axios.get("http://localhost:3001/item/read")
        produtos.value = resposta.data.db
        
    }
    onMounted ( () => {
        BuscarProdutos()
    })

    // Sugestão de estudo: funções filter, forEach e map

   


</script>

<template>
    <div class="flex">
        <div v-for="produto in produtos">                                     
            <Mesa class="flex" 
                :adicionaAoCarrinho="adicionaAoCarrinho"
                :produto="produto"
            />                      
        </div>                            
    </div>
</template>


