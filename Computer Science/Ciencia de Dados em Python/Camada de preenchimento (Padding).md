Um aspecto que a CNN trata é que o centro de cada [[kernel em Aprendizado de maquinas]] possa se sobrepor ao elemento mais externo da submatriz de entrada. Isso é feito por meio de uma técnica chamada de preenchimento, mais conhecida pelo nome original em inglês (_padding_), sendo mais comumente usada a de **preenchimento com zeros**.

Exemplo: 

![](https://stecine.azureedge.net/repositorio/00212ti/04164/img/img3.jpg)


---
 Comentário

As arquiteturas CNN utilizam o **preenchimento zero** para manter as dimensões da matriz de entrada e aplicar mais camadas no modelo. Sem o preenchimento de zero, cada mapa de características sucessivo ficaria menor após a aplicação da operação de convolução.

---
