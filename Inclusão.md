Quando o comportamento sempre se repetir em mais de um caso de uso

### Exemplo:

1. Sistema Bancário (Caixa Eletrônico ou Internet Banking)

- **Caso de Uso Base:** `Sacar Dinheiro`

- **Caso de Uso Incluído:** `Validar Senha` (ou `Verificar Saldo`)

- **Explicação:** Sempre que o cliente tenta sacar dinheiro, o sistema **obrigatoriamente** precisa validar a senha e checar o saldo antes de entregar as cédulas. O saque não existe sem essa etapa de segurança.

- **Representação:** `Sacar Dinheiro` → `<<include>>` → `Validar Senha`