
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

## Estrutura do projeto

![[Pasted image 20260618212707.png]]


# O que é um Componente no React?

Um componente é apenas uma **função JavaScript que retorna HTML** (tecnicamente chamado de JSX).

A ideia central é dividir o layout do seu site em pequenos blocos independentes e reutilizáveis. Em vez de escrever centenas de linhas de código em um único arquivo, você cria blocos isolados.

🏢 Pages vs. Components (A grande diferença)

No seu projeto, você tem (ou terá) duas pastas: `pages` e `components`. Elas guardam códigos parecidos, mas com propósitos totalmente diferentes:

1. **Pasta `pages/` (As Telas):** São os componentes que representam uma **tela cheia** do seu site. Eles são amarrados diretamente a uma URL (rota) no seu `App.jsx` (ex: `Home.jsx`, `Sobre.jsx`).
2. **Pasta `components/` (Os Blocos):** São os pedaços que compõem essas telas. Eles **não** têm rotas próprias. Eles são criados ali para serem "carimbados" e reutilizados dentro das suas páginas (ex: uma `Navbar`, um `Botao`, um `CardProjetos`).

---

