<script setup>

    import ('~/assets/css/monte-sua-festa.css')
    import ('~/assets/css/animate.min.css')
    import axios from 'axios';

    const params = defineProps(["adicionaAoCarrinho"])
    console.log(params)
    const produtos = reactive([])
    async function BuscarProdutos(){

        const resposta = await axios.get("http://localhost:3000/item/read")
        
        produtos.value = resposta.data.db
        console.log(produtos.value)
    }
    onMounted ( () => {
        BuscarProdutos()
    })

    // Sugestão de estudo: funções filter, forEach e map

    let lista = ref("decoracao")
    let produtos_festa = ref("decoracao")
    let produts =ref("false")
    let filtro = ref("")
    console.log(filtro)

    function alteraFiltro(valor){
        filtro.value = valor;
    }

    const filtros_decoracao = reactive([
    {nome:"Decorção de Futebol", filtro:"decoração_fut"},
    {nome:"Decoração de Casamento com Flores", filtro:"decoração_casam"}
    ])

    const filtros_itens_festa = reactive([
    {nome:"Mesas", filtro:"item_mesas"},
    {nome:"Toalhas", filtro:"item_toalhas"},
    {nome:"Pratos", filtro:"item_pratos"},
    {nome:"Talheres", filtro:"item_talheres"},
    {nome:"Cadeiras", filtro:"item_cadeiras"}
    ])
    
    const filtros_comida = reactive([
    {nome:"Salgados", filtro:"comida_salgados"},
    {nome:"Doces", filtro:"comida_doces"},
    {nome:"Bebidas", filtro:"comida_bebidas"},
    ])
    
    function disponivel(id){
        params.produtos[id].disponivel = true;
    }

    function decoracao(){

        lista.value = "decoracao";
        produtos_festa.value = "decoracao";
        produts = true;

    }

    function itens_festa(){

        produtos_festa.value = "decoracao";
        lista.value = "itens_festa";

    }

    function comida(){

        lista.value = "comida";
        produtos_festa.value = "decoracao";

    }

</script>

<template>
    
    <div class="container">
            //
            <div class="lateral">
                <ul>Monte seu evento:

                    <ul class="filha"><button v-on:click="decoracao()">Decoração</button></ul>
                    <hr> 
                    <ul class="filha"><button v-on:click="itens_festa()">Itens para a festa</button></ul>
                    <hr> 
                    <ul class="filha"><button v-on:click="comida()">Comida</button></ul> 
                            
                </ul>
            </div>

            <div class="produtos">

                <div class=" animate__animated animate__fadeInLeft animate__faster espaco" v-if=" lista == 'decoracao'">

                    <p>Filtros:</p>
                    <div class="flex_filtros">
                    <p v-for="filtro_decoracao in filtros_decoracao">
                       <input type="radio" name="objetivo" v-on:change="alteraFiltro(filtro_decoracao.filtro)" />{{ filtro_decoracao.nome }}
                    </p>
                    </div>
                        
                        <div class="flex">

                            <div v-for="produto in produtos">
                                
                                <Mesa class="flex" v-bind:adicionaAoCarrinho="adicionaAoCarrinho"  v-if="filtro == produto.tipo || filtro == ''" v-bind:produtos="produto" v-bind:disponivel="disponivel" />
                            
                            </div>                            
                        </div>
                </div>
                
                <div class=" animate__animated animate__fadeInLeft" v-if=" lista == 'itens_festa'">

                    <p>Filtros:</p>
                    <div class="flex_filtros">
                    <p v-for="filtro_item in filtros_itens_festa">
                       <input type="radio" name="objetivo" v-on:change="alteraFiltro(filtro_item.filtro)"/>{{ filtro_item.nome }}
                    </p>
                    </div>

                        <div class="flex">

                            <div v-for="produto in produtos">
                                <Mesa class="flex"  v-if="filtro == produto.tipo || filtro == ''" v-bind:produtos="produto" v-bind:disponivel="disponivel" />
                                
                            </div>
                    
                        </div>
                </div>

                <div class="animate__animated animate__fadeInLeft" v-if=" lista == 'comida'">

                    <p>Filtros:</p>
                    <div class="flex_filtros">
                    <p v-for="filtros_comida in filtros_comida">
                       <input type="radio" name="objetivo" v-on:change="alteraFiltro(filtros_comida.filtro)"/>{{ filtros_comida.nome }}
                    </p>
                    </div>
                    
                    <div class="flex">

                        <div v-for="produto in produtos">
                                
                            <Mesa class="flex"  v-if="filtro == produto.tipo || filtro == ''" v-bind:produtos="produto" v-bind:disponivel="disponivel" />
                                
                        </div>

                    </div>
                
               
                </div>

        </div>
    </div>

</template>


