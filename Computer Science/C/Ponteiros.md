
- Variáveis que armazenam endereços de memória.
- Funcionam como coordenadas que direcionam para locais específicos na memória do computador.

É uma variável especial que guarda o **endereço de memória** de outra variável, em vez de armazenar um valor direto. Pense nele como uma seta que aponta para o local exato onde um dado está guardado na memória RAM do computador

### Exemplo:

```c
#include <stdio.h>

int main() {
    int numero = 10;    // Uma variável comum
    int *ponteiro;      // Declaração de um ponteiro para inteiro

    ponteiro = &numero; // O ponteiro recebe o endereço de memória de 'numero'

    printf("Valor original de numero: %d\n", numero);
    printf("Endereco de memoria de numero: %p\n", (void*)&numero);
    printf("Valor guardado no ponteiro: %p\n", (void*)ponteiro);

    // Modificando o valor de 'numero' ATRAVÉS do ponteiro
    *ponteiro = 25; 

    printf("Novo valor de numero: %d\n", numero);

    return 0;
}

```