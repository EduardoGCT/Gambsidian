
## Relacionamentos no diagrama de classes

São fundamentais para representar as interações entre as classes de um sistema orientado a objetos. Além disso, os relacionamentos no diagrama de classes descrevem como as classes estão conectadas umas às outras e ajudam a definir a estrutura e o comportamento do sistema. No contexto da modelagem UML, os principais tipos de relacionamentos incluem associação, agregação, composição, herança e dependência.

Compreender esses relacionamentos ajuda a desenvolver um modelo preciso e coerente do sistema, permitindo que os desenvolvedores identifiquem e capturem de maneira eficaz as dependências e interações entre as diferentes partes do software.

Neste vídeo, você vai conferir as classes que se relacionam com outras classes, pois os objetos originados a partir delas trocam informações uns com os outros.

Você já viu que especificar uma classe diz respeito a definir seus atributos e operações. Mas classes não existem isoladas, elas só fazem sentido quando se relacionam a outras, pois os objetos originados a partir delas trocam informações uns com os outros; e nisso reside a implementação de um sistema orientado a objetos.

Dizemos que os objetos colaboram uns com os outros. O desenho do diagrama de classes mostra como os objetos instanciados a partir dessas classes podem se relacionar. Existem diferentes tipos de relacionamentos possíveis, bem como diversos detalhes que podem ser acrescentados no diagrama para melhorar sua semântica. Trataremos deles a seguir.

A forma de relacionamento mais comum é chamada de associação e é representada no diagrama de classes por uma linha (normalmente um segmento de reta) ligando as classes às quais pertencem os objetos relacionados.

A Imagem 3 adiante ilustra associações entre classes: Cliente faz Pedido; Professor ministra Disciplina.

![](https://stecine.azureedge.net/repositorio/00212ti/02034/img/img17.jpg)

Imagem 3: Associações simples entre classes.

Mas qual é o significado dessas associações? Quando ligamos as classes Cliente e Pedido significa que, durante a execução do sistema, haverá a possibilidade de troca de mensagens entre objetos dessas classes.

As associações possuem diversas características que podem ser representadas, por escolha do analista, para prover um melhor entendimento do modelo. Vamos conhecê-las a seguir:

### Nome

Conforme a Imagem 3 mostra, os nomes das associações (ministra, faz) descrevem a relação que é estabelecida entre os objetos das classes associadas. Normalmente, são usados verbos ou expressões verbais para nomear associações.

### Multiplicidades

As associações permitem representar a informação dos limites inferior e superior da quantidade de objetos aos quais outro objeto pode estar associado: são as chamadas multiplicidades.

Cada associação em um diagrama de classes possui duas multiplicidades, uma em cada extremo da linha que a representa. Os símbolos que representam uma multiplicidade são apresentados na tabela a seguir:

|   |   |
|---|---|
|Apenas 1|1..1 (ou 1)|
|Zero ou Muitos|0..* (ou *)|
|Um ou Muitos|1..*|
|Zero ou Um|0..1|
|Intervalo Específico|li..ls|

Tabela: Multiplicidades em um diagrama de classes.  
Flavia Maria Santoro.

Na Imagem 4 a seguir, mostramos o exemplo com as multiplicidades correspondentes. Esses novos diagramas expressam mais do que o anterior: eles informam que um professor pode ministrar nenhuma (zero) e no máximo três disciplinas (0..3). Uma disciplina precisa ser ministrada por pelo menos um professor, mas pode ser ministrada por muitos (1..*).

Já um cliente pode fazer nenhum (zero) pedido, sem um limite máximo (0..*), e um pedido precisa ser feito por um cliente (1). Veja as multiplicidades:

![](https://stecine.azureedge.net/repositorio/00212ti/02034/img/img18.jpg)

Imagem 4: Associações simples entre classes com multiplicidades.

### Tipo de participação

Indica a necessidade ou não da existência dessa associação entre objetos. A participação pode ser **obrigatória** ou **opcional**.

Se o valor mínimo da multiplicidade de uma associação é igual a 1 (um), significa que a participação é obrigatória. Caso contrário, a participação é opcional.

A participação de Cliente e Professor nos exemplos da Imagem 4 é obrigatória, e a de Disciplina e Pedido é opcional. Isso significa que pode existir professores e clientes sem necessariamente estarem ministrando disciplinas ou fazendo pedidos.

### Direção da leitura

A direção de leitura indica como a associação deve ser lida. Essa direção é representada por um pequeno triângulo posicionado próximo a um dos lados do nome da associação (como nos exemplos da Imagem 4).

### Papéis

Quando um objeto participa de uma associação, ele tem um papel específico nela.

Uma característica complementar à utilização de nomes e de direções de leitura é a indicação de papéis (roles) para cada uma das classes participantes em uma associação.