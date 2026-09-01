
O fork é uma chamada de sistema é uma chamada de sistema (**system call**) usada para criar um novo processo, duplicando o processo atual

O que o `fork()` faz?

- **Duplicação:** O processo que chama o `fork()` é o **processo pai**. O sistema operacional cria uma cópia quase exata dele, chamada de **processo filho** (espaço de memória, variáveis, descritores de arquivo e código).

- **Retorno duplo:** A função é chamada uma única vez pelo pai, mas **retorna duas vezes**: uma vez no processo pai e outra vez no processo filho.

- **Identificação:** Como o código executado após o `fork()` é o mesmo para ambos, o valor de retorno da função serve para diferenciar quem é quem:
    - Retorna **`0`** para o **processo filho**.
    - Retorna o **PID** (identificador) do filho para o **processo pai**.
    - Retorna **`-1`** se houver erro na criação do processo.