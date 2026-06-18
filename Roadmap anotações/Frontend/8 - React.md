
# How to start a project in React

Para iniciar um projeto React dentro da sua pasta de `frontend` existente, a forma mais rápida e recomendada atualmente é utilizar o **Vite**. Ele é extremamente rápido para criar e rodar a aplicação.

- Acesse a sua pasta de frontend:  
    `cd frontend`
- Crie o novo projeto React usando o Vite (substitua `meu-app` pelo nome que desejar para a pasta do seu projeto):  
    `npm create vite@latest meu-app -- --template react`  
    _(Ou `--template react-ts` se você preferir usar TypeScript)_
- Entre na pasta recém-criada:  
    `cd meu-app`
- Instale as dependências:  
    `npm install`
- Inicie o servidor de desenvolvimento:  
    `npm run dev`