Segmento de código que pode ser acessado por apenas um processo por vez, uma seção crítica contém variáveis compartilhadas que precisam ser sincronizadas para manter a consistência dos dados. 

- Três requisitos devem ser atendidos para resolver o problema da seção crítica. 
1. [[Exclusão mútua]]
2. [[Progresso]]
3. [[Espera limitada]]

---

- É possível utilizar dois tipos de solução para resolver o problema de seção crítica:
1. [[Solução de Peterson]]
2. [[Semáforos]]

### Exemplo:

```portugol
faça

{

Entrada da seção

Seção crítica

Saída da seção

Restante da seção

} enquanto(VERDADEIRO);
```