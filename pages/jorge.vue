<template>
    <div class="purchase-container">
      <div class="header">
        <h1>Compra do Veículo Jeep</h1>
      </div>
  
      <div class="vehicle-details">
        <img src="https://www.jeep.com.br/content/dam/jaguar/jeep/jeep-brasil/2021/compass/2021/jeep-compass-2021-1.jpg" alt="Jeep Compass" class="vehicle-image">
        <div class="vehicle-info">
          <h2>Jeep Combosta</h2>
          <p>O SUV que combina tecnologia e conforto.</p>
          <span class="price">Preço: R$ 150.000,00</span>
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
            <label for="date">Data da Compra:</label>
            <input type="date" id="date" v-model="purchaseDate" required>
          </div>
          <button type="submit" class="buy-button">Finalizar Compra</button>
        </form>
      </div>
    </div>
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
        purchaseDate: ''
      };
    },
    methods: {
      processPurchase() {
        alert(`Compra realizada com sucesso para ${this.customer.name}!\nData da Compra: ${this.purchaseDate}`);
        // Aqui você pode adicionar lógica para processar o pagamento ou enviar os dados para o servidor
      }
    }
  }
  </script>
  
  <style scoped>
  .purchase-container {
    max-width: 800px;
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
  
  .vehicle-details {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
  }
  
  .vehicle-image {
    width: 200px;
    height: auto;
    border-radius: 10px;
    margin-right: 20px;
  }
  
  .vehicle-info {
    flex: 1;
  }
  
  .vehicle-info h2 {
    margin: 0;
  }
  
  .price {
    font-size: 1.5em;
    color: #0074D9; /* Azul Jeep */
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
    background-color: #0074D9; /* Azul Jeep */
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  .buy-button:hover {
    background-color: #005bb5; /* Cor ao passar o mouse */
  }
  </style>
  