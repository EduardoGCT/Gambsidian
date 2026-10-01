Aplicada quando dois ou mais casos de uso possuam comportamentos comuns. 

### Exemplos: 

1. Sistema de Pagamento (E-commerce)

- **Caso de Uso Pai (Geral):** `Processar Pagamento`
- **Casos de Uso Filhos (Especializados):** `Pagar com Cartão de Crédito`, `Pagar com Pix` e `Pagar com Boleto`
- **Explicação:** Todos os três realizam a ação de pagar (herdam essa lógica), mas a forma como o sistema processa o Pix (gera QR Code) é diferente de como processa o Boleto (gera código de barras).
- **Representação:** `Pagar com Pix` ➔ 🛆 ➔ `Processar Pagamento` _(A ponta da seta triangular aponta para o pai)_