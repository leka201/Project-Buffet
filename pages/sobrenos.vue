<template>

  
    <main>
        <section class="sobre">
            <h2>Quem Somos</h2>
            <p>
                Nós somos uma empresa comprometida com a excelência e a inovação. Nossa missão é entregar soluções que façam a diferença na vida das pessoas e das empresas.
            </p>
        </section>
        <section class="valores">
            <h2>Nossos Princípios</h2>
            <div class="valores-lista">
                <div class="valor">
                    <h3>Inovação</h3>
                    <p>Buscamos sempre o novo e o melhor. Em nosso buffet, estamos constantemente introduzindo 
                        pratos criativos e tendências gastronômicas para surpreender seus convidados.</p>
                </div>
                <div class="valor">
                    <h3>Qualidade</h3>
                    <p>Nosso compromisso é com a excelência em tudo que fazemos. Desde a seleção rigorosa 
                        dos ingredientes até a apresentação final dos pratos, garantimos que cada detalhe 
                        seja impecável. Trabalhamos apenas com fornecedores confiáveis e de renome, que compartilham 
                        nossa paixão por qualidade..</p>
                </div>
                <div class="valor">
                    <h3>Transparência</h3>
                    <p> Valorizamos a honestidade e a clareza nas nossas relações. Acreditamos que a 
                        transparência é fundamental para construir uma relação de confiança com nossos 
                        clientes. Desde o primeiro contato até a finalização do evento, garantimos que 
                        todas as informações, incluindo preços, opções de menu e políticas, sejam 
                        comunicadas de forma clara e acessível.</p>
                </div>
            </div>
        </section>
        <section class="equipe">
            <h2>Nossa Equipe</h2>
            <p>
                Contamos com um time altamente qualificado e motivado, pronto para atender suas necessidades. 
                Nossa equipe é composta por chefs experientes que trazem uma rica bagagem culinária, 
                especialistas em atendimento ao cliente que garantem uma experiência agradável desde o primeiro contato ate o fim. 
            </p>
        </section>
    </main>
    <br>
    <br>
    <br>
    
    <footer>
        <p>&copy; 2024 Soulfest.<br>
            <br>
           <strong>Obrigado</strong><br>
            Carlão<br>
            Conrado<br>
            Marcius<br>
            ChatGPT<br></p>
    </footer>


</template>



<style>

body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
}

header {
    background-color: #4B0082; /* Roxo */
    color: white;
    padding: 20px 0;
}

.container {
    max-width: 1200px;
    margin: auto;
    padding: 0 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

nav ul {
    list-style: none;
    display: flex;
}

nav ul li {
    margin-left: 20px;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

main {
    padding: 20px;
    max-width: 800px;
    margin: auto;
}

h1, h2 {
    color: #4B0082; /* Roxo */
}

.valores-lista {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
}

.valor {
    flex: 1;
    background-color: #f2f2f2;
    margin: 0 10px;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

footer {
    text-align: center;
    padding: 10px 0;
    background-color: #4B0082; /* Roxo */
    color: white;
    position: relative;
    bottom: 0;
    width: 100%;
}

</style>