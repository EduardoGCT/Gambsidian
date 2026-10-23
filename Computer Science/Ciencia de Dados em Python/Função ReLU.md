A função de ativação linear retificada (_Rectified Linear Unit_ ou Unidade Linear Retificada) é dada por: 

![[Pasted image 20261022223757.png]]

Ela serve para introduzir **não-linearidade** no modelo, permitindo que a rede aprenda padrões complexos e dados que não podem ser resolvidos apenas por linhas retas.


### Como ela funciona matematicamente

A fórmula da ReLU é simples: ela retorna o **valor máximo entre 0 e a entrada** (x): 

- Se o dado de entrada for **negativo** (x < 0), a função transforma esse valor em **0**.

- Se o dado de entrada for **positivo ou zero** (x ≥ 0), a função **mantém o próprio valor** inalterado.

---
### Por que ela é importante nos dados em IA?

- **Não-linearidade:** Sem funções de ativação como a ReLU, uma rede neural seria apenas uma sequência de multiplicações e somas lineares, o que limitaria sua capacidade de entender imagens, textos ou sons.

- **Evita o "desaparecimento do gradiente":** Em funções antigas (como _sigmoid_ ou _tanh_), os valores "saturam" e os gradientes ficam quase zerados em números muito altos ou baixos, travando o aprendizado. Na ReLU, para valores positivos, o gradiente é sempre constante (1), o que faz o treinamento ser muito mais rápido e eficiente.

- **Eficiência computacional:** Como ela só precisa comparar se o número é maior que zero, o cálculo é extremamente leve para o processador ou placa de vídeo.

---
### Exemplo prático

Imagine um neurônio recebendo os seguintes valores de entrada após uma camada de dados:

- Entrada: `-5` → Saída da ReLU: **`0`**

- Entrada: `-1.2` → Saída da ReLU: **`0`**

- Entrada: `0` → Saída da ReLU: **`0`**

- Entrada: `3.5` → Saída da ReLU: **`3.5`**

- Entrada: `10.8` → Saída da ReLU: **`10.8`**