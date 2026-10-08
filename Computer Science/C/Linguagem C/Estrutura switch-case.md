
- Limpa e organiza decisões baseadas em uma única variável, especialmente quando lidamos com muitas escolhas diretas baseadas em um única variável. 

### Exemplo 

```c
#include <stdio.h>

  

int main () {

int escolha;

  

printf("Escolha seu produto: 1 para Agua, 2 para Refrigerante, 3 para Suco\n");

scanf("%d", &escolha);

  

switch (escolha) {

case 1:

printf("Você escolheu Agua.\n");

break;

case 2:

printf("Voce escolheu Refrigerante\n");

break;

case 3:

printf("Voce escolheu Suco\n");

break;

default:

printf("Opcao invalida\n");

}

  

return 0;

}
```