<template>
    <main>
      <section class="servicos">
        <h2>Nossos Serviços</h2>
        <p>
          Oferecemos uma ampla gama de serviços para atender às suas necessidades e tornar seu evento
          inesquecível. Confira abaixo as opções que temos para você!
        </p>
        <div class="servicos-lista">
          <div class="servico">
            <h3>Buffet Completo</h3>
            <p>
              Um menu cuidadosamente elaborado para surpreender seus convidados, com pratos que vão
              desde entradas sofisticadas até sobremesas deliciosas.
            </p>
          </div>
          <div class="servico">
            <h3>Decoração Temática</h3>
            <p>
              Transformamos o ambiente do seu evento com decorações criativas e temáticas,
              adaptadas ao estilo e às preferências do cliente.
            </p>
          </div>
          <div class="servico">
            <h3>Bebidas Premium</h3>
            <p>
              Um cardápio exclusivo de bebidas, incluindo coquetéis personalizados, vinhos e
              destilados de alta qualidade.
            </p>
          </div>
          <div class="servico">
            <h3>Serviço de Garçons</h3>
            <p>
              Profissionais treinados para oferecer um atendimento impecável, garantindo conforto e
              praticidade para todos os convidados.
            </p>
          </div>
        </div>
      </section>
    </main>
    <br />
    <footer>
      <p>&copy; 2024 Soulfest.<br /><br /><strong>Obrigado</strong><br /> Carlão<br /> Conrado<br /> Marcius<br /> ChatGPT<br /></p>
    </footer>
  </template>
  
  <script>
  export default {
    name: "ServicosPage",
  };
  </script>
  
  <style scoped>
  body {
    font-family: "Arial", sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
  }
  
  main {
    padding: 20px;
    max-width: 800px;
    margin: auto;
  }
  
  h1,
  h2 {
    color: #4b0082; /* Roxo */
  }
  
  .servicos-lista {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    margin-top: 20px;
  }
  
  .servico {
    flex: 1 1 calc(50% - 20px);
    background-color: #f2f2f2;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  }
  
  footer {
    text-align: center;
    padding: 10px 0;
    background-color: #4b0082; /* Roxo */
    color: white;
    position: relative;
    bottom: 0;
    width: 100%;
  }
  </style>
  