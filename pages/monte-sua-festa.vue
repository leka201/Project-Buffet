<script setup>

    import ('~/assets/css/monte-sua-festa.css')
    import ('~/assets/css/animate.min.css')
    import axios from 'axios';

    const params = defineProps(["adicionaAoCarrinho"])
    console.log(params)
    const produtos = reactive([])
    async function BuscarProdutos(){

        const resposta = await axios.get("http://localhost:3001/item/read")
        console.log("item")
        console.log(resposta.data.db)
        produtos.value = resposta.data.db
        console.log(produtos.value )
    }
    onMounted ( () => {
        console.log("entrou")
        BuscarProdutos()
    })

    // Sugestão de estudo: funções filter, forEach e map

    let lista = ref("decorations")
    let produtos_festa = ref("decorations")
    let produts =ref("false")
    let filtro = ref("")
    console.log(filtro)

    function alteraFiltro(valor){
        filtro.value = valor;
    }

    const filtros_decorations = reactive([
    {name:"Decoração de Futebol"},
    {name:"Decoração de Casamento com Flores"}
    ])

    const filtros_items = reactive([
    {name:"Mesas", filtro:"item_mesas"},
    {name:"Toalhas", filtro:"item_toalhas"},
    {name:"Pratos", filtro:"item_pratos"},
    {name:"Talheres", filtro:"item_talheres"},
    {name:"Cadeiras", filtro:"item_cadeiras"}
    ])
    
    const filtros_food = reactive([
    {name:"Salgados", filtro:"food_salgados"},
    {name:"Doces", filtro:"food_doces"},
    {name:"Bebidas", filtro:"food_bebidas"},
    ])

    function decorations(){

        lista.value = "decorations";
        produtos_festa.value = "decorations";
        produts = true;

    }

    function items(){

        produtos_festa.value = "decorations";
        lista.value = "items";

    }

    function food(){

        lista.value = "food";
        produtos_festa.value = "decorations";

    }

</script>

<template>
    
    <div class="container">
            //
            <div class="lateral">
                <ul>Monte seu evento:

                    <ul class="filha"><button v-on:click="decorations()">Decoração</button></ul>
                    <hr> 
                    <ul class="filha"><button v-on:click="items()">Itens para a festa</button></ul>
                    <hr> 
                    <ul class="filha"><button v-on:click="food()">Comida</button></ul> 
                            
                </ul>
            </div>

            <div class="produtos">

                <div class=" animate__animated animate__fadeInLeft animate__faster espaco" v-if=" lista == 'decorations'">

                    <p>Filtros:</p>
                    <div class="flex_filtros">
                    <p v-for="filtro_decorations in filtros_decorations">
                       <input type="radio" name="objetivo" v-on:change="alteraFiltro(filtro_decorations.filtro)" />{{ filtro_decorations.name }}
                    </p>
                    </div>
                        
                        <div class="flex">

                            <div v-for="produto in produtos.value">                                     
                                <Mesa class="flex" v-bind:adicionaAoCarrinho="adicionaAoCarrinho"  v-if="filtro == produto.decorations || filtro == ''" v-bind:produtos="produto"/>                      
                            </div>                            
                        </div>
                </div>
                
                <div class=" animate__animated animate__fadeInLeft" v-if=" lista == 'items'">

                    <p>Filtros:</p>
                    <div class="flex_filtros">
                    <p v-for="filtro_item in filtros_items">
                       <input type="radio" name="objetivo" v-on:change="alteraFiltro(filtro_item.filtro)"/>{{ filtro_item.name }}
                    </p>
                    </div>

                        <div class="flex">

                            <div v-for="produto in produtos">
                                <Mesa class="flex"  v-if="filtro == produto.decorations || filtro == ''" v-bind:produtos="produto"/>
                                
                            </div>
                    
                        </div>
                </div>

                <div class="animate__animated animate__fadeInLeft" v-if=" lista == 'food'">

                    <p>Filtros:</p>
                    <div class="flex_filtros">
                    <p v-for="filtros_food in filtros_food">
                       <input type="radio" name="objetivo" v-on:change="alteraFiltro(filtros_food.filtro)"/>{{ filtros_food.name }}
                    </p>
                    </div>
                    
                    <div class="flex">

                        <div v-for="produto in produtos">
                                
                            <Mesa class="flex"  v-if="filtro == produto.decorations || filtro == ''" v-bind:produtos="produto"/>
                                
                        </div>

                    </div>
                
               
                </div>

        </div>
    </div>

</template>


