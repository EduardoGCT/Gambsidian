Executa um bloco de código repetidamente. Ela faz isso apenas enquanto uma condição informada continuar sendo verdadeira. Assim que a condição vira falsa, o programa para o looping e segue em frente.

### Exemplo:
```c
#include <stdio.h>

int main () {
	int contador = 0;
	
	while (contador < 5) {
		printf("Numero %d\n", contador);
		contador++;
	}
	
	return 0;
}
```