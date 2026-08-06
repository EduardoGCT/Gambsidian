
## Função das Estruturas Condicionais

- Permitem que o código tome decisões baseadas em condições específicas.
- Instruções principais: 
		1. if
		2. else
		3. else if


### Exemplo prático 

```c
#include <stdio.h>

  

int main (){

int temperatura;

  

printf("Digite a temperatura atual: ");

scanf("%d", &temperatura);

  

if (temperatura < 0){

printf("Esta muito frio\n");

} else if (temperatura >= 0 && temperatura < 20){

printf("Esta frio\n");

} else if (temperatura >= 20 && temperatura < 30){

printf("Esta agradavel.\n");

} else {

printf("Esta quente!\n");

}

return 0;

}

```

