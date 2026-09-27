
Como o script oficial de instalação do Ollama baixou os arquivos diretamente da internet e configurou tudo manualmente por baixo dos panos, nós precisamos fazer o caminho inverso para limpar o seu sistema. Como você usa Arch Linux, fazer essa limpeza manual é bem direto.

**1.Parar e desativar o serviço no sistema:**Evita conflitos e arquivos travados durante a exclusão.

Primeiro, encerre o processo do Ollama que está rodando em segundo plano.

Bash

```
sudo systemctl stop ollama
sudo systemctl disable ollama
```

**2.Remover os arquivos do serviço e o executável:**

Delete o arquivo de configuração do systemd e o binário principal do Ollama.

Bash

```
sudo rm /etc/systemd/system/ollama.service
sudo rm $(which ollama)
```

**3.Apagar os modelos e arquivos residuais:**Passo importante para liberar espaço no SSD.

Os modelos de inteligência artificial são pesados e ficam armazenados em pastas específicas criadas pelo script.

Bash

```
sudo rm -r /usr/share/ollama
sudo rm -r ~/.ollama
```

**4.Remover o usuário e o grupo:**

Para deixar o sistema limpo, remova o usuário `ollama` e o grupo dedicado que o script criou para rodar o serviço.

Bash

```
sudo userdel ollama
sudo groupdel ollama
```

Se você decidir instalar novamente no futuro para aproveitar sua RX 7600 nativamente, recomendo usar o `pacman` (como mostrei lá na primeira resposta). É muito mais fácil de gerenciar, atualizar e desinstalar pelo padrão do Arch Linux sem precisar caçar arquivos depois.