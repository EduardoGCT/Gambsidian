- Sequências de elementos do mesmo tipo, acessados por índices.
- Analogia: Vagões numerados de um trem de carga.

É uma estrutura de dados que guarda uma coleção de vários valores do mesmo tipo sob um único nome de variável. Cada valor fica em uma posição específica chamada **índice**, que na maioria das linguagens começa no número zero.

### Exemplo:

```c
#include <stdio.h>

int main () {
	int numeros[10]; //define um vetor de 10 números
	for (int i = 0; i < 10; i++){
		numeros[i] = i;
		printf("%d ", numeros[i]);
	}
	
	return 0;
}
```
