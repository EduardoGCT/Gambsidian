(Re-allocation)

Modifica o tamanho de um bloco de memória que já foi alocado anteriormente por 
`malloc` ou `calloc`. Ela tenta expandir ou reduzir o espaço atual, preservando os 
dados antigos.

### Exemplo:

```c
// Redimensiona o vetor anterior de 5 para 10 inteiros
vetor = (int *) realloc(vetor, 10 * sizeof(int));

```