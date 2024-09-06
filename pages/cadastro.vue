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

            <input type="checkbox"> Feminino <required>
            <br/>
                
            <input type="checkbox"> Masculino <required>
            <br/>
                    
            <input type="checkbox"> Não informar <required>
            <br/>
                        
        </label>

        <hr/>

        <p><strong> Crie uma senha</strong></p>
        <a class="letramenor">Entre 8 a 12 caracters:</a> <input  minlength="8"required> 
        <br/> 
        <br/>

        <label> 
                        
            <input type="checkbox"> Aceito os termos,pagar 50% antes da montagem <required>
            <br/>
            <input type="checkbox"> receber mensagem via sms
            <br/>
            <input type="checkbox"> receber e-mails promocionais
            <br/>
                                    
        </label>
        <br/>

        
        
    </form>

</template>