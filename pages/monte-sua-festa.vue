<script setup>

import ('assets/css/monte-sua-festa.css')

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

                    <ul class="filha"><button v-on:click="tipo_festa()">Tipo de festa</button></ul> 
                    <hr> 
                    <ul class="filha"><button v-on:click="decoracao()">Decoração</button></ul>
                    <hr> 
                    <ul class="filha"><button v-on:click="itens_festa()">Itens para a festa</button></ul>
                    <hr> 
                    <ul class="filha"><button v-on:click="comida()">Comida</button></ul> 
                            
                </ul>
            </div>


            <div class="produtos">

        <div v-if=" lista == 'tipo_festa'">
            <p>Filtros:</p>
                <input type="radio" name="objetivo"/>Festa Infantil
                <input type="radio" name="objetivo"/>Festa Adolescente
                <input type="radio" name="objetivo"/>Festa Adulto

        </div>

        <div v-if=" lista == 'decoracao'">

            <p>Filtros:</p>
                <input type="radio" name="objetivo"/>Futebol
                <input type="radio" name="objetivo"/>#####

        </div>

        <div v-if=" lista == 'itens_festa'">

            <p>Filtros:</p>
                <input type="radio" name="objetivo"/>Cadeiras e Mesas
                <input type="radio" name="objetivo"/>#####

        </div>

        <div v-if=" lista == 'comida'">

            <p>Filtros:</p>
                <input type="radio" name="objetivo"/>Salgados
                <input type="radio" name="objetivo"/>Refrigerantes
                <input type="radio" name="objetivo"/>Bolos

        </div>

                <!-- <p>
                    Itens selecionados:
                    <br>
                    <br>
                    Tipo de festa:
                    <br>
                    <br>
                    Festa Infantil 
                </p>

                <p>
                    Decoração:
                    <br>
                    Futebol
                </p>

                <p>
                    Itens para a festa:
                    <br>
                    Cadeiras e Mesas
                </p>
                
                <p>
                    Comida:
                    <br>
                    Salgados
                    <br>
                    Refrigerantes
                </p> -->
            </div>

    </div>

</template>


<!-- <style>

animate__fadeInLeft

</style> -->