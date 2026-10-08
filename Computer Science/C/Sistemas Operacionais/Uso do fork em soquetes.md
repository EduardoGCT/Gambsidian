
O uso do `fork()` em programação de redes em C é a abordagem clássica para criar **servidores concorrentes**, permitindo que o servidor atenda múltiplos clientes simultaneamente em vez de colocá-los em uma fila de espera.

**O Fluxo de Execução**

- **Ouvir:** O processo principal (Pai) configura um soquete ouvinte (`listen`) e pausa na chamada `accept`, esperando a chegada de um cliente.
    
- **Conectar e Bifurcar:** Quando um cliente se conecta, o `accept` retorna um novo descritor de arquivo (file descriptor) exclusivo para aquela comunicação. O servidor então chama o `fork()`.
    
- **Divisão de Tarefas:** O sistema operacional cria um processo Filho exato ao Pai. Ambos continuam a execução a partir do `fork()`, mas o Filho atende o cliente enquanto o Pai volta a escutar a porta.

### Exemplo:

```C
while (1) {
    // 1. Aguarda a conexão de um cliente
    int client_fd = accept(server_fd, (struct sockaddr*)&client_addr, &client_len);

    // 2. Cria um novo processo para lidar com a conexão
    pid_t pid = fork();

    if (pid == 0) {
        // --- PROCESSO FILHO ---
        close(server_fd);          // Filho não precisa ouvir novas conexões
        
        tratar_cliente(client_fd); // Função que envia/recebe dados (send/recv)
        
        close(client_fd);          // Encerra a conexão com este cliente
        exit(0);                   // Termina o processo filho
    } 
    else if (pid > 0) {
        // --- PROCESSO PAI ---
        close(client_fd);          // Pai delega o cliente, logo fecha sua cópia
        // O loop reinicia e volta para o accept()
    }
}	
```
