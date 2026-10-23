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