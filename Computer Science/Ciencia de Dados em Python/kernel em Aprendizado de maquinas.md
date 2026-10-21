1. Kernel no Aprendizado de Machine Learning (_Kernel Methods_)

Em modelos como o **SVM (Support Vector Machine)** ou PCA, o kernel é uma função matemática que ajuda a resolver problemas não-lineares.

- **O Problema:** Às vezes, os dados em um gráfico 2D estão todos misturados e você não consegue passar uma linha reta simples para separá-los em categorias (dados não linearmente separáveis). 
- **O "Kernel Trick" (Truque do Kernel):** Em vez de calcular e projetar os dados fisicamente em um espaço de 3 ou mais dimensões (o que gasta muito processamento), a função kernel calcula a **similaridade** entre os pontos como se eles já estivessem nesse espaço superior. 
- **Exemplos comuns:**
    - **Linear:** Para dados que já separam bem em linha reta.
    - **Polinomial (Polynomial):** Cria curvas e dobras baseadas em graus.
    - **RBF (Radial Basis Function / Gaussiano):** Muito usado para criar fronteiras complexas e circulares ao redor de grupos de dados. 