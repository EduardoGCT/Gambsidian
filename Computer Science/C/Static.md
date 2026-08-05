Preserva seu valor entre chamadas de função. Exemplo: Manter estados como um contador de visitas.

## Exemplo de uso em chamadas de funções:

```c
#include <stdio.h>

  

//função que utiliza um contador estático

void incrementaContador(){

static int contador = 0;

contador++;

printf("Contador: %d\n", contador);

}

  

int main (){

incrementaContador();

incrementaContador();

incrementaContador();

incrementaContador();

  

return 0;
}
```