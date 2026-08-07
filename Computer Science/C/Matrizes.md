
- Uma matriz é uma estrutura de dados multidimensional (geralmente bidimensional) organizada em linhas e colunas. Ela funciona como uma tabela ou um vetor de vetores, permitindo armazenar vários valores do mesmo tipo sob um único nome de variável e acessá-los usando dois ou mais índices.

### Exemplo: 

```c
#include <stdio.h>

int main () {
	int tabela[4][5]; //define uma matriz de 4 linhas e 5 colunas
	for (int i = 0; i < 4; i++){
		for (int j = 0; j < 5; j++){
			tabela[i][j] = i * j;
			printf("%d ", tabela[i][j]);
		}
		prinf("\n");	
	}
	
	return 0;
}
```
