<template>
    <footer class="footer">
      <div class="footer-container">
        <div class="footer-section">
          <h3>Sobre Nós</h3>
          <p>Somos especialistas em criar festas inesquecíveis. Transformamos seus sonhos em realidade!</p>
        </div>
  
        <div class="footer-section">
          <h3>Links Úteis</h3>
          <ul>
            <li><a href="/sobrenos">Sobre Nós</a></li>
            <li><a href="/servicos">Serviços</a></li>
            <li><a href="/contato">Contato</a></li>
            <li><a href="/politica-de-privacidade">Política de Privacidade</a></li>
          </ul>
        </div>
  
        <div class="footer-section">
          <h3>Contato</h3>
          <p>Email: soulfest@gmail.com</p>
          <p>Telefone: (16) 9 9244-8042</p>
        </div>
  
        <div class="footer-section">
          <h3>Inscreva-se na nossa Lista de novidades</h3>
          <form @submit.prevent="subscribe">
            <input type="email" placeholder="Seu email" required>
            <button type="submit">Inscrever</button>
          </form>
        </div>
      </div>
  
      <div class="footer-bottom">
        <p>&copy; 2024 Seu Site. Todos os direitos reservados.</p>
        <div class="social-icons">
          <a href="https://facebook.com" target="_blank">Facebook</a>
          <a href="https://instagram.com" target="_blank">Instagram</a>
          <a href="https://twitter.com" target="_blank">Twwiter
            
          </a>
        </div>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    methods: {
      subscribe() {
        alert('Inscrição realizada com sucesso!'); // Aqui você pode integrar a lógica de inscrição
      }
    }
  }
  </script>
  
  <style scoped>
  .footer {
    background-color: #282c34; /* Cor de fundo do rodapé */
    color: white; /* Cor do texto */
    padding: 40px 20px; /* Espaçamento interno */
    text-align: left; /* Alinhamento do texto à esquerda */
  }
  
  .footer-container {
    display: flex;
    justify-content: space-between; /* Espaço entre as seções */
    flex-wrap: wrap; /* Permite que as seções quebrem para a linha seguinte se necessário */
  }
  
  .footer-section {
    flex: 1; /* Cada seção ocupa espaço igual */
    margin: 10px; /* Margem entre as seções */
  }
  
  .footer-section h3 {
    margin-bottom: 15px; /* Espaçamento abaixo do título */
  }
  
  .footer-section p,
  .footer-section ul {
    margin: 0; /* Remove margens padrão */
  }
  
  .footer-section ul {
    list-style-type: none; /* Remove marcadores da lista */
    padding: 0; /* Remove preenchimento da lista */
  }
  
  .footer-section ul li {
    margin: 10px 0; /* Espaçamento entre os itens da lista */
  }
  
  .footer-section a {
    color: white; /* Cor dos links */
    text-decoration: none; /* Remove underline dos links */
  }
  
  .footer-section a:hover {
    text-decoration: underline; /* Adiciona underline ao passar o mouse */
  }
  
  .footer-bottom {
    margin-top: 20px; /* Espaçamento acima do rodapé inferior */
    text-align: center; /* Centraliza o texto */
  }
  
  .footer-bottom .social-icons {
    margin-top: 10px; /* Espaçamento acima dos ícones sociais */
  }
  
  .footer-bottom .social-icons a {
    margin: 0 10px; /* Espaçamento entre os ícones sociais */
    color: white; /* Cor dos ícones sociais */
    text-decoration: none; /* Remove underline dos links */
  }
  
  .footer-bottom .social-icons a:hover {
    text-decoration: underline; /* Adiciona underline ao passar o mouse */
  }
  
  footer form {
    display: flex; /* Flexbox para alinhar o input e o botão */
  }
  
  footer input[type="email"] {
    padding: 10px; /* Espaçamento interno */
    border: none; /* Remove borda padrão */
    border-radius: 5px 0 0 5px; /* Bordas arredondadas */
    flex: 1; /* Faz o input ocupar todo o espaço disponível */
  }
  
  footer button {
    padding: 10px 15px; /* Espaçamento interno */
    border: none; /* Remove borda padrão */
    border-radius: 0 5px 5px 0; /* Bordas arredondadas */
    background-color: purple; /* Cor de fundo do botão */
    color: white; /* Cor do texto do botão */
    cursor: pointer; /* Muda o cursor ao passar sobre o botão */
  }
  
  footer button:hover {
    background-color: #21a1f1; /* Cor do botão ao passar o mouse */
  }
  </style>
  