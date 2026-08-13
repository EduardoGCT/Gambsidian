(Deallocation)

Libera a memória alocada dinamicamente de volta para o sistema operacional. É 
obrigatório usar para evitar o **vazamento de memória** (_memory leak_).

### Exemplo:

```c
// Libera os espaços criados nos exemplos anteriores
free(p);
free(vetor);

```