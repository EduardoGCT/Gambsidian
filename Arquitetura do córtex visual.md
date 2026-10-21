
### 1. Principais Conceitos Biológicos e seus Paralelos Computacionais

O córtex visual processa estímulos luminosos de forma modular e em camadas sucessivas. Na disciplina, destacam-se três pilares fundamentais dessa estrutura:

- **Campos Receptivos Locais (_Receptive Fields_):**
    
    - _No cérebro:_ Os neurônios do córtex visual primário (V1) não olham para a imagem inteira de uma vez; cada neurônio responde apenas a uma pequena região específica do campo visual.
        
    - _Na rede neural:_ Isso inspirou os **filtros/kernels de convolução**, que operam localmente sobre matrizes de pixels, em vez de conectar cada pixel de entrada a todos os neurônios da camada seguinte (como nas redes MLP tradicionais).
        
- **Células Simples e Complexas:**
    
    - _Células Simples:_ Detectam características direcionadas, como bordas, linhas e orientações específicas em uma posição exata. (Correspondem às primeiras **camadas convolucionais** com ativação ReLU).
        
    - _Células Complexas:_ Possuem campos receptivos maiores e respondem a características semelhantes, mas exibem **invariância à translação** (ou seja, se a linha se mover ligeiramente, o neurônio ainda dispara). (Correspondem às **camadas de Pooling**, como o _Max Pooling_).
        
- **Hierarquia de Extração de Características:**
    
    - O processamento visual avança por áreas corticais progressivas (V1 $\rightarrow$ V2 $\rightarrow$ V4 $\rightarrow$ Corte Inferotemporal).
        
    - As camadas iniciais detectam linhas e cantos básicos; as intermediárias combinam isso em texturas e formas geométricas; e as camadas profundas reconhecem objetos complexos completos (faces, animais, carros).
        

### 2. Mapeamento Direto para uma CNN

Quando estudamos essa arquitetura aplicada, a estrutura do modelo computacional reflete diretamente a biologia:

| **Camada do Cérebro / Biologia**              | **Camada Correspondente na CNN**        | **Função Principal**                                                            |
| --------------------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------- |
| **Retina e V1 (Camadas Iniciais)**            | Camadas Convolucionais Iniciais         | Extração de bordas, cantos e gradientes de cor locais.                          |
| **V2 e V4 (Camadas Intermediárias)**          | Camadas Convolucionais Profundas        | Combinação de padrões para formar texturas, partes de objetos e formas.         |
| **Córtex Temporal Inferior (Camadas Finais)** | Camadas Totalmente Conectadas (_Dense_) | Representação de alto nível e classificação final do objeto detectado.          |
| **Invariância Espacial Biológica**            | Camadas de _Pooling_ (_Max/Average_)    | Redução de dimensionalidade mantendo a robustez a pequenas mudanças de posição. |