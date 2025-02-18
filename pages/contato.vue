<template>
    <main>
      <section class="contato">
        <h2>Entre em Contato</h2>
        <p>
          Estamos aqui para ajudar! Entre em contato conosco para esclarecer dúvidas, solicitar um orçamento ou 
          simplesmente saber mais sobre nossos serviços.
        </p>
        <form class="form-contato">
          <div class="form-group">
            <label for="nome">Nome:</label>
            <input type="text" id="nome" name="nome" placeholder="Seu nome" required />
          </div>
          <div class="form-group">
            <label for="email">E-mail:</label>
            <input type="email" id="email" name="email" placeholder="Seu e-mail" required />
          </div>
          <div class="form-group">
            <label for="mensagem">Mensagem:</label>
            <textarea id="mensagem" name="mensagem" placeholder="Sua mensagem" rows="5" required></textarea>
          </div>
          <button type="submit" class="btn-enviar">Enviar</button>
        </form>
      </section>
    </main>
    <br />
    <footer>
      <p>&copy; 2024 Soulfest.<br /><br /><strong>Obrigado</strong><br /> Carlão<br /> Conrado<br /> Marcius<br /> ChatGPT<br /></p>
    </footer>
  </template>
  
  <script>
  export default {
    name: "ContatoPage",
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
  
  .form-contato {
    margin-top: 20px;
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  label {
    display: block;
    font-weight: bold;
    margin-bottom: 5px;
  }
  
  input,
  textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  button {
    background-color: #4b0082; /* Roxo */
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #3a006b;
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
  