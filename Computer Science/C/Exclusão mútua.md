Apenas um processo pode estar na seção crítica de cada vez.

### Exemplo:

```C
faça
{
    Enquanto (TestAndSetBloqueio(& bloqueio))
    ; //faça nada
        Seção crítica
    Bloqueio=FALSO;
        Restante da seção
    }enquanto(VERDADEIRO)


```