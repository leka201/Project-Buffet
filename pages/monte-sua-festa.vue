<script setup>

    import ('~/assets/css/monte-sua-festa.css')
    import ('~/assets/css/animate.min.css')

    let lista = ref("tipo_festa")

    function tipo_festa(){

        lista.value = "tipo_festa";

    }

    function decoracao(){

        lista.value = "decoracao";

    }

    function itens_festa(){

        lista.value = "itens_festa";

    }

    function comida(){

        lista.value = "comida";

    }

</script>

<template>

    <div class="container">

            <div>
                <ul>Monte seu evento:

                    <ul class="filha"><button v-on:click="decoracao()">Decoração</button></ul>
                    <hr> 
                    <ul class="filha"><button v-on:click="itens_festa()">Itens para a festa</button></ul>
                    <hr> 
                    <ul class="filha"><button v-on:click="comida()">Comida</button></ul> 
                            
                </ul>
            </div>


            <div class="produtos">

                <div class=" animate__animated animate__fadeInLeft animate__faster" v-if=" lista == 'decoracao'">

                    <p>Filtros:</p>
                        <input type="radio" name="objetivo"/>Futebol
                        <input type="radio" name="objetivo"/>#####

                </div>
                
                <Produtos/>

                <div class=" animate__animated animate__fadeInLeft" v-if=" lista == 'itens_festa'">

                    <p>Filtros:</p>
                        <input type="radio" name="objetivo"/>Cadeiras e Mesas
                        <input type="radio" name="objetivo"/>#####

                </div>

                <div class="animate__animated animate__fadeInLeft" v-if=" lista == 'comida'">

                    <p>Filtros:</p>
                    <input type="radio" name="objetivo"/>Salgados
                    <input type="radio" name="objetivo"/>Refrigerantes
                    <input type="radio" name="objetivo"/>Bolos

                </div>

               
            </div>

    </div>

</template>


