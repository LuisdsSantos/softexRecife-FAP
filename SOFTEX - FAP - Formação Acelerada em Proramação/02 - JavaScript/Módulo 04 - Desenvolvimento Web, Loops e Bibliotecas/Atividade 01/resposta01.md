# Atividade

Crie um código com um objeto chamado “Banco”. Ele deverá ter propriedades que incluem conta, saldo, tipo de conta e agência e os
seus métodos devem ser: buscar saldo, depósito, saque e número da conta.

Observações:

- buscar saldo deve retornar o valor atual do saldo;

- para o depósito, você deverá passar um valor como parâmetro e adicioná-lo no saldo final do objeto;

- para o saque, você deverá passar um valor como parâmetro e subtraí-lo no saldo final do objeto;

- o número da conta deve retornar o número da conta.


## Resposta

```javascript
// Definindo o objeto Banco
const Banco = {
    conta: "12345-6",
    saldo: 1000,
    tipoConta: "Corrente",
    agencia: "7890",
  
    // Método para buscar saldo
    buscarSaldo: function () {
      return this.saldo;
    },
  
    // Método para realizar um depósito
    deposito: function (valor) {
      if (valor > 0) {
        this.saldo += valor;
        return `Depósito de R$ ${valor} realizado com sucesso. Saldo atual: R$ ${this.saldo}`;
      } else {
        return "Valor inválido para depósito.";
      }
    },
  
    // Método para realizar um saque
    saque: function (valor) {
      if (valor > 0 && valor <= this.saldo) {
        this.saldo -= valor;
        return `Saque de R$ ${valor} realizado com sucesso. Saldo atual: R$ ${this.saldo}`;
      } else {
        return "Saldo insuficiente ou valor de saque inválido.";
      }
    },
  
    // Método para obter o número da conta
    numeroDaConta: function () {
      return this.conta;
    },
  };
  
  // Exemplo de utilização
  console.log("Número da Conta: " + Banco.numeroDaConta());
  console.log("Saldo atual: R$ " + Banco.buscarSaldo());
  console.log(Banco.deposito(500));
  console.log(Banco.saque(200));
  console.log("Saldo atual: R$ " + Banco.buscarSaldo());
  
```