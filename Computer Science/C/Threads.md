
## O que são Threads?

**Threads** são unidades de execução dentro de um processo, permitindo multitarefas.

Ao abrir um programa, um processo é criado. Um thread é uma **unidade de execução** dentro desse processo:

- Um programa com um único thread tem um único thread (geralmente chamado de **thread principal**).

- Um programa com múltiplos threads realiza multitarefas, executando cálculos simultaneamente e acelerando o programa.

A maioria dos sistemas operacionais modernos suporta multiprocessamento e execução de processos em múltiplos threads, conhecidos como **multithreading**. Isso aumenta o desempenho e a escalabilidade, mas também a complexidade do código e a dificuldade de depuração.

Existem dois tipos de threads:
1. [[Threads de usuário]]
2. [[Threads do kernel]]

---

- Threads são representados por Thread Control Blocks (TCBs), que contêm alguns elementos. 

-  [[Thread ID]]
-  [[Thread states]]
