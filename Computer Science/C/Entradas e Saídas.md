# Funções de Entrada e Saída em C (`<stdio.h>`)

Na linguagem C, as operações de entrada (ler dados do teclado, arquivos, etc.) e saída (exibir dados na tela, gravar em arquivos, etc.) são fornecidas pela biblioteca padrão através do cabeçalho `#include <stdio.h>`.

---

## 1. Entrada e Saída Formatada (Console)

Essas funções utilizam **especificadores de formato** (como `%d`, `%f`, `%s`, `%c`) para converter dados entre texto e tipos de dados primitivos.

### `printf()` — *Print Formatted*
* **Tipo:** Saída
* **O que faz:** Imprime texto e valores de variáveis formatados na saída padrão (`stdout` / tela).
* **Sintaxe:** `int printf(const char *formato, ...);`
* **Exemplo:**
  ```c
  int idade = 25;
  printf("Idade: %d anos\n", idade);
  ```

### `scanf()` — *Scan Formatted*
* **Tipo:** Entrada
* **O que faz:** Lê dados formatados da entrada padrão (`stdin` / teclado) e armazena nas variáveis através de seus endereços de memória (`&`).
* **Sintaxe:** `int scanf(const char *formato, ...);`
* **Atenção:** Para strings (`%s`), ele para a leitura no primeiro espaço em branco.
* **Exemplo:**
  ```c
  int numero;
  printf("Digite um número: ");
  scanf("%d", &numero);
  ```

---

## 2. Entrada e Saída de Caracteres Individuais

Funções otimizadas para manipulação de um único caractere por vez.

### `getchar()`
* **Tipo:** Entrada
* **O que faz:** Lê o próximo caractere disponível no buffer do teclado (`stdin`) e o retorna como um `int` (ou `EOF` em caso de fim de arquivo/erro).
* **Exemplo:**
  ```c
  char c = getchar();
  ```

### `putchar()`
* **Tipo:** Saída
* **O que faz:** Escreve um único caractere na saída padrão (`stdout`).
* **Exemplo:**
  ```c
  char c = 'A';
  putchar(c); // Exibe: A
  ```

### `getc()` / `fgetc()`
* **Tipo:** Entrada
* **O que faz:** Lê um único caractere de um fluxo especificado (pode ser `stdin` ou um arquivo aberto). `getc()` pode ser implementada como macro, enquanto `fgetc()` é estritamente uma função.
* **Exemplo:**
  ```c
  int ch = fgetc(stdin);
  ```

### `putc()` / `fputc()`
* **Tipo:** Saída
* **O que faz:** Escreve um único caractere em um fluxo especificado (`stdout` ou arquivo).
* **Exemplo:**
  ```c
  fputc('Z', stdout);
  ```

---

## 3. Entrada e Saída de Cadeias de Caracteres (Strings)

### `puts()` — *Put String*
* **Tipo:** Saída
* **O que faz:** Imprime uma string na tela seguida automaticamente por uma quebra de linha (`\n`).
* **Exemplo:**
  ```c
  puts("Olá, Mundo!");
  ```

### `fgets()` — *File Get String*
* **Tipo:** Entrada
* **O que faz:** Lê uma linha inteira (incluindo espaços) de um fluxo (como `stdin` ou arquivo) até o tamanho limite definido, evitando *buffer overflow*.
* **Sintaxe:** `char *fgets(char *str, int n, FILE *stream);`
* **Exemplo:**
  ```c
  char nome[50];
  printf("Digite seu nome completo: ");
  fgets(nome, sizeof(nome), stdin);
  ```

> ⚠️ **Nota de Segurança:** A antiga função `gets()` foi descontinuada e removida do padrão C11 por ser insegura (não limita o tamanho da entrada). Use sempre `fgets()`.

---

## 4. Entrada e Saída Formatada em Strings na Memória

Essas funções não leem nem escrevem no console/arquivo, mas sim diretamente em buffers de memória (arrays de `char`).

### `sprintf()` / `snprintf()` — *String Print Formatted*
* **Tipo:** Saída (em memória)
* **O que faz:** Monta e formata uma string e a armazena em um array em vez de imprimir na tela. `snprintf` é a versão segura que limita a quantidade de bytes gravados.
* **Exemplo:**
  ```c
  char mensagem[100];
  int pontos = 500;
  snprintf(mensagem, sizeof(mensagem), "Pontuação atual: %d", pontos);
  ```

### `sscanf()` — *String Scan Formatted*
* **Tipo:** Entrada (de memória)
* **O que faz:** Lê e extrai dados formatados a partir de uma string existente.
* **Exemplo:**
  ```c
  char data[] = "19 08 2026";
  int dia, mes, ano;
  sscanf(data, "%d %d %d", &dia, &mes, &ano);
  ```

---

## 5. Entrada e Saída com Arquivos (`FILE *`)

### Formatadas: `fprintf()` e `fscanf()`
* **`fprintf()`:** Funciona exatamente como o `printf()`, mas grava em um arquivo especificado (`FILE *`).
* **`fscanf()`:** Funciona exatamente como o `scanf()`, mas lê dados de um arquivo especificado.

### Binárias / Blocos de Dados: `fread()` e `fwrite()`
* **`fwrite()`:** Escreve blocos de memória brutos (structs, arrays, dados binários) diretamente em um arquivo.
* **`fread()`:** Lê blocos de memória brutos diretamente de um arquivo.

---

## 📌 Resumo Rápido

| Função | Tipo | Destino/Origem | Lê/Escreve Espaços? | Uso Recomendado |
| :--- | :--- | :--- | :--- | :--- |
| `printf` | Saída | Terminal | N/A | Exibir texto formatado |
| `scanf` | Entrada | Teclado | Não (para `%s`) | Ler tipos primitivos (`int`, `float`, etc.) |
| `fgets` | Entrada | Teclado/Arquivo | Sim | Ler strings e frases completas com segurança |
| `puts` | Saída | Terminal | N/A | Imprimir texto simples com `\n` ao final |
| `getchar` | Entrada | Teclado | Sim | Ler um caractere ou capturar o `\n` residual |
| `putchar` | Saída | Terminal | N/A | Exibir um único caractere |
| `fprintf`/`fscanf`| Saída/Entrada | Arquivo | Depende do formato | Manipulação de arquivos de texto formatados |
| `fwrite`/`fread` | Saída/Entrada | Arquivo | N/A (binário) | Manipulação de dados estruturados/binários |