Um processo no sistema operacional usa recursos de três maneiras: **solicita um recurso**, **utiliza o recurso** e **libera o recurso**. No deadlock, um conjunto de processos fica bloqueado, pois cada processo está retendo um recurso e aguardando outro, que está sendo retido por outro processo.

Em um exemplo clássico, temos dois trens em direções opostas no mesmo trilho; nenhum deles pode se mover até que o outro saia do caminho.

Se houver um sistema que tem como recursos duas unidades de disco e dois processos, P0 e P1, que têm, cada um, uma unidade de disco, um precisa do outro. Se ambos bloquearem os recursos, os processos entrarão em deadlock: o processo 1 está mantendo o recurso 1 e aguardando o recurso 2; esse é adquirido pelo processo 2; e esse está aguardando o recurso 1.

![[Pasted image 20260902222408.jpg]]

