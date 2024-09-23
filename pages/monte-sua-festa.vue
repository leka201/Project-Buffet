<script setup>

    import ('~/assets/css/monte-sua-festa.css')
    import ('~/assets/css/animate.min.css')

    const params = defineProps(["produtos", "adicionaAoCarrinho"])
    console.log(params)

    let lista = ref("decoracao")
    let produtos_festa = ref("decoracao")
    let produts =ref("false")
    
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
                        <input type="radio" name="objetivo"/>Futebol
                        <input type="radio" name="objetivo"/>#####

                        <div class="flex">

                            <Mesa class="flex" v-if="produtos_festa == 'decoracao'" v-bind:produtos="params.produtos[0]" v-bind:disponivel="disponivel" />
                            
                        </div>
                </div>
                
                <div class=" animate__animated animate__fadeInLeft" v-if=" lista == 'itens_festa'">

                    <p>Filtros:</p>
                        <input type="radio" name="objetivo"/>Cadeiras e Mesas
                        <input type="radio" name="objetivo"/>#####

                        <div class="flex">

                        <Mesa class="flex" v-if="produtos_festa == 'decoracao'" v-bind:produtos="params.produtos[0]" v-bind:disponivel="disponivel" />
                    
                        </div>
                </div>

                <div class="animate__animated animate__fadeInLeft" v-if=" lista == 'comida'">

                    <p>Filtros:</p>
                    <input type="radio" name="objetivo"/>Salgados
                    <input type="radio" name="objetivo"/>Refrigerantes
                    <input type="radio" name="objetivo"/>Bolos

                <!-- </div> -->
                    <div class="flex">

                    <Mesa class="flex" v-if="produtos_festa == 'decoracao'" v-bind:produtos="params.produtos[0]" v-bind:disponivel="disponivel" />
                   
                    </div>
                
               
                </div>

        </div>
    </div>

</template>


