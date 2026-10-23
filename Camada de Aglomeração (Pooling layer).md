A camada de aglomeração – normalmente referenciada por (**POOL**) – é uma operação que tem por objetivo a redução da quantidade de neurônios para as camadas posteriores.

A POOL, em geral, é aplicada após uma camada de convolução.

A ideia da redução da imagem de entrada é diminuir a carga computacional, o uso de memória e o número de parâmetros. É uma forma de se prevenir em relação a um problema dos modelos de aprendizado de máquina supervisionado: o risco de **sobreajuste**, mais conhecido como _overfitting_, que ocorre quando o modelo fica superespecializado nos dados de treinamento e não consegue generalizar os resultados.

As duas principais operações _pooling_ são:

## _Max pooling_

Obtém o maior valor de uma submatriz. Ela **preserva** os recursos detectados.

## _Average pooling_

Obtém a média dos valores de uma submatriz. Logo, ela **não preserva** os recursos detectados.

Na imagem a seguir, mostramos um exemplo das duas operações de _pooling_.

![](https://stecine.azureedge.net/repositorio/00212ti/04164/img/img4.jpg)

Camada de _pooling_.

No caso da imagem de exemplo, observe o seguinte:

1. 
    
    Para calcular o _max pooling_, tivemos que verificar quem era o maior elemento dentro de uma submatriz e colocar o valor na saída correspondente.
    
2. 
    
    No caso do _average pooling_, tivemos que calcular a média dos elementos de cada submatriz e associá-la à respectiva posição de saída.
    
3. 
    
    Devemos notar que a matriz de entrada possuía quatro linhas e quatro colunas, ou seja, **dezesseis elementos**.
    
4. 
    
    Agora, a matriz resultante de cada operação de aglomeração possui duas linhas e dois elementos, ou seja, um total de **quatro elementos** em cada matriz.
    

Da mesma forma que tivemos que definir o parâmetro do tamanho do passo da **camada de convolução**, também precisamos fazer o mesmo para a **camada de aglomeração**, além de definir as dimensões da matriz de saída.

assignment_ind

## Comentário

Então, pelo que vimos, cabe destacar que um neurônio de _pooling_ não tem pesos. O que ele faz é agregar as entradas por intermédio de uma **função de agregação**, como o máximo ou a média.

#### Camada totalmente conectada

Camada que, normalmente, é aplicada no final de uma CNN. Ela opera sobre uma entrada plana e cada uma das entradas é conectada a todos os nós da camada consecutiva de neurônios. Veja:

![](https://stecine.azureedge.net/repositorio/00212ti/04164/img/img5.jpg)

Camada totalmente conectada.

Analisando a imagem da esquerda para a direita, vemos uma imagem retangular que é transformada para uma matriz coluna. Em seguida, cada célula de entrada é conectada a todos os neurônios da camada seguinte.

As camadas totalmente conectadas também são chamadas de camadas densas.