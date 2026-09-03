Podem ser 0 ou 1, funcionando como bloqueios mutex para garantir exclusão mútua.

### Exemplo:
```c
faça
{
    Aguarde(mutex);
        Seção crítica
    Sinal(mutex);
        Restante da seção
}enquanto(VERDADEIRO);

```