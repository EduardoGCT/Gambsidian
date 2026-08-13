(Memory Allocation)

Aloca um bloco contínuo de memória com o tamanho exato solicitado em bytes. O 
conteúdo desse bloco inicial não é limpo, ou seja, ele contém **lixo de memória**.

### Exemplo: 
```c
// Aloca espaço para 1 número inteiro
int *p = (int *) malloc(sizeof(int));

if (p != NULL) {
    *p = 42; // Atribui valor
}

```