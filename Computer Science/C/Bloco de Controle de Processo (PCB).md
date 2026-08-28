É uma estrutura de dados criada pelo sistema operacional para guardar todas as informações essenciais sobre um processo que está na memória.

- Funciona como uma identidade e o prontuário de um processo. 
- Permite que o processador para um trabalho no meio, mude para outro e depois volte exatamente do ponto onde parou. 
- Ajuda na organização do multitarefa.

### O que fica guardado dentro da PCB?

- **Identificador (PID):** O número único que identifica o processo.

- **Estado do processo:** Mostra se ele está executando, pronto para executar, aguardando algo (como leitura de disco) ou finalizado.

- **Contador de programa (Program Counter):** O endereço da próxima instrução que o processo precisa executar.

- **Registradores da CPU:** Valores que estavam salvos nos registradores do processador quando o processo foi interrompido.

- **Informações de memória:** Dados sobre onde estão alocadas as variáveis e o código do processo na RAM (como ponteiros de memória e tabelas de páginas).

- **Informações de E/S (Entrada e Saída):** Lista de arquivos abertos ou dispositivos que o processo está usando.

- **Informações de contabilidade:** Tempo de CPU usado, limites de tempo e dados de uso de recursos.