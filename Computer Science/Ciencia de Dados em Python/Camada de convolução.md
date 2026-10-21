A camada de convolução é responsável por mapear as características da imagem que vamos fornecer para a CNN. 

A camada de convolução é referida pela expressão CONV.

A camada CONV faz uso de filtros que realizam operações de convolução enquanto ela processa a imagem de entrada. 

![[Pasted image 20261020225104.jpg]]

Temos uma imagem de entrada que é representada por uma matriz de valores binários (valores 0 ou 1) de seis linhas e seis colunas.

Em seguida, selecionamos um bloco da imagem para aplicar um filtro. O operador “*” representa a operação de convolução.

No caso, o valor “25” na matriz de resultado foi obtido a partir do seguinte cálculo:
![[Pasted image 20261020225510.png]]
O processo deve continuar até que todos os quadros da imagem sejam tratados.

Esses deslocamentos na imagem de entrada são chamados de **tamanho do passo**, que, em inglês, é referenciado como _stride_.

 Atenção
A camada de convolução tem como hiperparâmetros os tamanhos do filtro e do passo. A saída resultante é chamada de **mapa de características**, ou **mapa de ativação**.

