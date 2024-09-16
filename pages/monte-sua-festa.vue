<script setup>

    import ('~/assets/css/monte-sua-festa.css')
    import ('~/assets/css/animate.min.css')

    const params = defineProps(["produtos"])

    let lista = ref("decoracao")
    
    function disponivel(id){
        params.produtos[id].disponivel = true;
    }

    function decoracao(){

        // lista.value = "decoracao";
        lista.value = "true"

    }

    function itens_festa(){

        lista.value = "itens_festa";
        lista.value = "true"

    }

    function comida(){

        // lista.value = "comida";
        lista.value = "true"

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

                <div class=" animate__animated animate__fadeInLeft animate__faster espaco" v-if=" lista == 'true & itens_festa'">

                    <p>Filtros:</p>
                        <input type="radio" name="objetivo"/>Futebol
                        <input type="radio" name="objetivo"/>#####

                </div>
                
                <div class=" animate__animated animate__fadeInLeft" v-if=" lista == 'true'">

                    <p>Filtros:</p>
                        <input type="radio" name="objetivo"/>Cadeiras e Mesas
                        <input type="radio" name="objetivo"/>#####

                </div>

                <div class="animate__animated animate__fadeInLeft" v-if=" lista == ''">

                    <p>Filtros:</p>
                    <input type="radio" name="objetivo"/>Salgados
                    <input type="radio" name="objetivo"/>Refrigerantes
                    <input type="radio" name="objetivo"/>Bolos

                </div>
                <div v-if=" lista == 'true'" class="flex">

                    <Mesa class="flex" v-bind:produtos="params.produtos[0]" v-bind:disponivel="disponivel" />
                    <Mesa class="flex" v-bind:produtos="params.produtos[1]" v-bind:disponivel="disponivel"/>
                    <Mesa class="flex" v-bind:produtos="params.produtos[2]" v-bind:disponivel="disponivel"/>
                    <Mesa class="flex" v-bind:produtos="params.produtos[3]" v-bind:disponivel="disponivel"/>
                    <Mesa class="flex" v-bind:produtos="params.produtos[4]" v-bind:disponivel="disponivel"/>
                
                </div>
                
               
            </div>

    </div>

</template>


