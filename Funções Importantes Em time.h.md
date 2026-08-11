## Funções para Manipulação de Tempo

- `strftime()`: Formata data e hora em struct tm para uma string.
- `difftime(): Calcula a diferença em segundo entre dois tempos (`time_t`).
- `asctime() e ctime()`: Convertem tempo para uma string legível. 


### Exemplo:

```c
#include <stdio.h>
#include <time.h>

int main () {
	time_t agora;
	
	time(&agora);
	
	printf("Hora atual: %s", ctime(&agora));
	
	return 0;
}
```