(Contiguous Allocation)

Aloca memória para um número específico de elementos de um determinado tamanho. Diferente do `malloc`, ela inicializa automaticamente todos os bits com **zero**.

### Exemplo:

```c
// Aloca um vetor de 5 inteiros e zera todos eles
int *vetor = (int *) calloc(5, sizeof(int));

// vetor[0] até vetor[4] já começam valendo 0

```