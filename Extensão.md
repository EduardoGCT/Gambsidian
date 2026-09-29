Quando o comportamento pode ser executado em algumas instâncias de um caso de uso.

### Exemplos: 

1. Sistema Bancário (Caixa Eletrônico)

- **Caso de Uso Base:** `Sacar Dinheiro`
- **Caso de Uso de Extensão:** `Cobrar Taxa de Saque`
- **Condição de Extensão:** Se o cliente excedeu o limite mensal de saques gratuitos.
- **Explicação:** O cliente consegue sacar dinheiro normalmente sem cobrar taxa. O caso de uso de cobrança só é ativado se a condição de limite estourado for verdadeira.

- **Representação:** `Cobrar Taxa de Saque` → `<<extend>>` → `Sacar Dinheiro` _(A seta aponta para o caso base)_