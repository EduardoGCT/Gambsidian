A função de tangente hiperbólica utiliza a função sigmoide na sua composição. Sua fórmula é dada por: 

![[Pasted image 20261022222827.png]]

é uma função matemática de **ativação** usada em **redes neurais** e processamento de dados. Ela transforma qualquer valor de entrada em um número no intervalo entre **-1 e 1**.

### Principais características nos dados

- **Centrada em Zero**: Diferente da função SIGMOID que varia de 0 e 1, a tanh varia entre -1 e 1. Isso significa que os dados ficam centralizados em torno de zero, facilitando o aprendizado e a convergência das camadas seguintes da rede neural.

- **Não linearidade:** Permite que o modelo aprenda padrões complexos e relações não lineares nos dados.

- **Vantagem sobre a Sigmóide:** Por ser centrada em zero, os gradientes costumam fluir melhor durante o treinamento em comparação com a função sigmóide.

- **Limitação (Desaparecimento do Gradiente):** Assim como a sigmóide, valores de entrada muito altos ou muito baixos empurram a saída para os limites (-1 ou 1), onde a inclinação (gradiente) fica quase zero, o que pode retardar ou travar o aprendizado em redes muito profundas.

