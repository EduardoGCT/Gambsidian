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

```c
#include <stdio.h>

#include <time.h>

#include <Windows.h>

  

int main(){

time_t inicion, fim;

  

time(&inicio);

printf("Tempo inicial capturado.\n");

  

//pausa simulada

printf("Esperando por 5 segundos...\n");

for (int i = 0; i < 5; i++){

printf("%d...\n", 5 - i);

Sleep(1000);

}

  

time (&fim);

printf("Tempo final capturado.\n");

  

double diferenca = difftime(fim, inicio);

  

printf e: %.f segundoszn(";A diferenca em segundos e: %.f segundoszn", diferenca);

  

return 0;

}
```