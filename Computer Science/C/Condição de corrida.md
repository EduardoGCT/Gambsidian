Ocorre quando vários processos acessam e manipulam dados simultaneamente, resultando em saídas imprevisíveis. Para evitar condições de corrida, seções críticas, em que o acesso a variáveis compartilhadas deve ser controlado, devem ser tradadas como instruções atômicas. O uso adequado de bloqueios ou variáveis atômicas também pode evitar condições de corrida.

### Exemplo:

Dois processos, P1 e P2, que compartilham uma variável (compartilhada = 10). Se P1 executa primeiro, incrementa a variável e entra em espera; P2, então, executa e decrementa a variável. Dependendo da ordem de execução, o valor final da variável pode ser 9 ou 11, resultando em dados inconsistentes.