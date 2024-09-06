


<template>
     <form>
        <div>
           
            <p class="espaco">Digite seu Nome:</p>
            <input  minlength="2" required>
           
            <p class="espaco">Digite seu Cpf:</p> 
           <input  minlength="11"required>
            
            <p class="espaco">Digite seu Email:</p>
            <input type ="email"required>
            
            <p class="espaco">Digite Cep:</p>
            <input  minlength="7"required>
            
            <p class="espaco">Digite seu endereço:</p>
            <input required>

            <p class="espaco">Digite seu bairro:</p>
            <input required>

            <p class="espaco">Digite sua cidade:</p>
            <input  minlength="3" required>
            
            <p class="espaco">Digite seu telefone:</p>
            <input  minlength="9" required>
            
            <p class="espaco">Data de nascimento:</p>
            <input type="date"  required>
           
        </div>
        <hr/>
        
        <label><p><strong>Informe genero:</strong></p>

            <input type="checkbox" required> Feminino 
            <br/>
                
            <input type="checkbox" required> Masculino 
            <br/>
                    
            <input type="checkbox" required> Não informar 
            <br/>
                        
        </label>

        <hr/>

        <p><strong> Crie uma senha</strong></p>
        <a class="letramenor">Entre 8 a 12 caracters:</a> <input  minlength="8"required> 
        <br/> 
        <br/>

        <label> 
                        
            <input type="checkbox"> Aceito os termos,pagar 50% antes da montagem 
            <br/>
            <input type="checkbox"> receber mensagem via sms
            <br/>
            <input type="checkbox"> receber e-mails promocionais
            <br/>
                                    
        </label>
        <br/>

        <button>Salvar e voltar ao login</button>

    </form>

</template>

<style scoped>
@import url("~/assets/css/cadastro.css");
</style>