
A alocação dinâmica de memória em C é o processo de reservar espaço na memória 
RAM **durante a execução** (tempo de execução) do programa, e não quando ele é 
compilado. Ela usa a região Heap e permite criar estruturas de tamanho flexível sob 
demanda, evitando desperdício.

- Usado na biblioteca <stdlib.h>

1. [[malloc]]
2. [[calloc]]
3. [[realloc]]
4. [[free]]

### Exemplo:
```c
#include <stdio.h>

int main () {
	int *numeros = (int *) malloc(10 * sizeof (int));
	
	if (numeros == NULL) {
		prinf("Erro ao alocar memoria\n");
		return 1;
	}
	
	for (int i = 0; i < 10; i++){
		numeros[i] = i;
		printf("Numero %d\n", i);
	}
	
	free(numeros);
	return 0;
}
```
