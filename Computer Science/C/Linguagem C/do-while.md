Executa um bloco de código ao menos uma vez e depois o repete enquanto uma condição específica continuar verdadeira. O teste da condição acontece no final do bloco, e não no início.

### Exemplo: 
```c
#include <stdio.h>

int main () {
	int contador = 0;
	
	do {
		printf("Numero %d\n", contador);
		contador++;
	} while (contador < 5);
	
	return 0;
}
```