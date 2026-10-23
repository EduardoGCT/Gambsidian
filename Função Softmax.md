Utilizada no final da CNN:

![[Pasted image 20261022224830.png]]

é uma operação matemática que transforma um vetor de pontuações brutas (chamadas de _logits_) em uma **distribuição de probabilidade** cujos valores somam exatamente 1 (ou 100%).

### Como ela funciona?

O processo acontece em duas etapas principais:

- **Exponenciação (\(e^{x}\)):** Aplica a função exponencial a cada valor do vetor de entrada. Isso garante que todos os números fiquem positivos e acentua as diferenças entre eles (valores maiores crescem muito mais rápido que os menores).

- **Normalização:** Divide o valor exponenciado de cada elemento pela soma das exponenciais de todos os elementos do vetor.

---
### Para que serve?

- **Classificação Multiclasse:** É muito usada na camada de saída de redes neurais quando o modelo precisa escolher **uma** entre várias classes mutuamente exclusivas (por exemplo: identificar se uma imagem mostra um gato, um cachorro ou um coelho).

- **Interpretação como Probabilidade:** Transforma saídas numéricas sem limites fixos (que podem ser negativas ou maiores que 1) em probabilidades reais entre 0 e 1. 

- **Mecanismos de Atenção e Transformers:** É utilizada para calcular pesos de atenção entre diferentes tokens ou partes de uma sequência em modelos de linguagem modernos

---

### Principais características

- **Soma igual a 1:** Cada saída individual representa a probabilidade de pertencer àquela classe, e a soma de todas as probabilidades do vetor resulta em 1. 
- **Interdependência:** Ao contrário da função _sigmoid_ (usada para classificação binária ou rótulos independentes), a alteração no valor de uma classe na softmax afeta diretamente a probabilidade das outras. 

### Exemplos:

Exemplo Numérico

Imagine que a sua rede neural gerou as seguintes pontuações brutas (_logits_) para uma imagem que pode ser um **Gato**, **Cachorro** ou **Pássaro**:

- **Gato:** 2.0

- **[Cachorro](https://www.google.com/search?kgmid=%2Fm%2F0bt9lr&q=Cachorro):** 1.0
- **Pássaro:** 0.1

Ao aplicar a função Softmax, esses números são transformados em probabilidades:

| Classe       | Logit (Entrada) | Cálculo Exponencial (\(e^{z}\)) | Probabilidade Softmax (Saída) |
| ------------ | --------------- | ------------------------------- | ----------------------------- |
| **Gato**     | 2.0             | \(e^{2.0} \approx 7.39\)        | **65,9%**                     |
| **Cachorro** | 1.0             | \(e^{1.0} \approx 2.72\)        | **24,2%**                     |
| **Pássaro**  | 0.1             | \(e^{0.1} \approx 1.11\)        | **9,9%**                      |
| **Soma**     | -               | **11.22** (Denominador)         | **100%** (1.0)                |

---

Código em Python

O código abaixo implementa a função de forma eficiente. Note o uso de `np.max(z)` para evitar o erro de _overflow_ (quando os números ficam grandes demais para a memória do computador):

python

``` python
import numpy as np

def softmax(z):
    # np.max(z) subtrai o maior valor para garantir estabilidade numérica
    exp_z = np.exp(z - np.max(z)) 
    return exp_z / np.sum(exp_z)

# Pontuações brutas (logits) da rede neural
logits = np.array([2.0, 1.0, 0.1])

# Aplica a função softmax
probabilidades = softmax(logits)

print("Probabilidades por classe:")
print(f"Gato:    {probabilidades[0]:.2%}")
print(f"Cachorro: {probabilidades[1]:.2%}")
print(f"Pássaro:  {probabilidades[2]:.2%}")
print(f"Soma total: {np.sum(probabilidades)}")
```