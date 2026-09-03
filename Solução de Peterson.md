Baseada em software, para o problema da seção crítica, utilizando duas variáveis compartilhadas.

[[Sinalizador booleano]]
[[Turn]]

### Exemplo:

```c
faça
{
    Flag[i]=VERDADEIRO
    Rodada=j
    Enquanto(flag[j] && rodada==j)
        Seção crítica
    Flag[i]=FALSO;
        Restante da seção
}enquanto(VERDADEIRO)

```