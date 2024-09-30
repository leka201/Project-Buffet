<template>
    <div class="purchase-container">
      <div class="header">
        <h1>Compra do Combo de Formatura</h1>
      </div>
  
      <div class="combo-details">
        <img src="https://cdn.prod.website-files.com/5fbd45a4128163fe7d9d9b0d/60c791dd48eb58937e0bc659_5.1.jpeg" alt="Combo Formatura" class="combo-image">
        <div class="combo-info">
          <h2>Combo Formatura</h2>
          <p>Pacote completo com jantar, decoração, fotos e animação.</p>
          <span class="price">Preço: R$ 1.500,00</span>
        </div>
      </div>
  
      <div class="purchase-form">
        <h3>Informações de Compra</h3>
        <form @submit.prevent="processPurchase">
          <div class="form-group">
            <label for="name">Nome:</label>
            <input type="text" id="name" v-model="customer.name" required>
          </div>
          <div class="form-group">
            <label for="email">Email:</label>
            <input type="email" id="email" v-model="customer.email" required>
          </div>
          <div class="form-group">
            <label for="phone">Telefone:</label>
            <input type="tel" id="phone" v-model="customer.phone" required>
          </div>
          <div class="form-group">
            <label for="date">Data da Formatura:</label>
            <input type="date" id="date" v-model="partyDate" required>
          </div>
          <button type="submit" class="buy-button">Finalizar Compra</button>
        </form>
      </div>
    </div>
    <br>   <br> <br>
  

  <Rodape />
  </template>
  
  <script>
  export default {
    data() {
      return {
        customer: {
          name: '',
          email: '',
          phone: ''
        },
        partyDate: ''
      };
    },
    methods: {
      processPurchase() {
        alert(`Compra realizada com sucesso para ${this.customer.name}!\nData da Formatura: ${this.partyDate}`);
        // Aqui você pode adicionar lógica para processar o pagamento ou enviar os dados para o servidor
      }
    }
  }
  </script>
  
  <style scoped>
  .purchase-container {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    background-color: #f9f9f9;
    border-radius: 10px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  }
  
  .header {
    text-align: center;
    margin-bottom: 20px;
  }
  
  .combo-details {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
  }
  
  .combo-image {
    width: 150px;
    height: auto;
    border-radius: 10px;
    margin-right: 20px;
  }
  
  .combo-info {
    flex: 1;
  }
  
  .combo-info h2 {
    margin: 0;
  }
  
  .price {
    font-size: 1.5em;
    color: #28a745;
    font-weight: bold;
  }
  
  .purchase-form {
    background-color: #ffffff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
  }
  
  input[type="text"],
  input[type="email"],
  input[type="tel"],
  input[type="date"] {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  .buy-button {
    padding: 10px 20px;
    background-color: #6E32A6;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  .buy-button:hover {
    background-color: #5b2b8c; /* Cor ao passar o mouse */
  }
  </style>
  