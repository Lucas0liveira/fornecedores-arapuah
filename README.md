# 🐝 Arapuá Marketplace

> Simulador educacional de pedidos B2B para aulas de logística do ensino médio.

O Arapuá é uma loja virtual fictícia onde alunos praticam o processo de compra entre empresas (B2B): exploram fornecedores, montam um carrinho de pedido e enviam via WhatsApp. O projeto também tem uma área administrativa onde professores e alunos gerenciam fornecedores e produtos.

---

## Sumário

- [O que você vai encontrar aqui](#o-que-você-vai-encontrar-aqui)
- [Tecnologias utilizadas](#tecnologias-utilizadas)
- [Rodando o projeto no seu computador](#rodando-o-projeto-no-seu-computador)
- [Como contribuir](#como-contribuir)
- [Estrutura de pastas](#estrutura-de-pastas)
- [Dúvidas frequentes](#dúvidas-frequentes)

---

## O que você vai encontrar aqui

| Tela | O que faz |
|---|---|
| **Página inicial** | Lista todos os fornecedores cadastrados |
| **Catálogo do fornecedor** | Produtos com filtro, busca e paginação |
| **Carrinho** | Revisão dos itens antes de pedir |
| **Revisão do pedido** | Monta a mensagem que vai ser enviada por WhatsApp |
| **Área admin** | Gerenciamento de fornecedores, produtos e alunos (acesso restrito) |

---

## Tecnologias utilizadas

Você não precisa entender tudo isso para contribuir, mas é bom saber o que existe:

| Tecnologia | Para que serve |
|---|---|
| **Next.js** | Framework principal — é ele que gera as páginas do site |
| **TypeScript** | Versão do JavaScript com verificação de tipos (ajuda a evitar erros) |
| **Tailwind CSS** | Sistema de estilos — classes prontas para deixar o visual bonito |
| **Supabase** | Banco de dados e autenticação (login dos professores e alunos) |
| **Zustand** | Gerencia o carrinho de compras |
| **Vercel** | Hospedagem do site (onde o site fica publicado na internet) |

---

## Rodando o projeto no seu computador

Siga os passos abaixo **na ordem**. Se travar em algum ponto, leia a seção [Dúvidas frequentes](#dúvidas-frequentes) ou abra uma Issue no GitHub.

### Passo 1 — Instale os programas necessários

Você vai precisar de três programas instalados:

1. **Node.js** (versão 20 ou mais recente)
   - Acesse [nodejs.org](https://nodejs.org) e baixe a versão **LTS** (a recomendada).
   - Durante a instalação, aceite todas as opções padrão.
   - Para confirmar que funcionou, abra o terminal e digite:
     ```
     node -v
     ```
     Deve aparecer algo como `v20.x.x`.

2. **Git**
   - Acesse [git-scm.com](https://git-scm.com) e baixe para Windows.
   - Durante a instalação, aceite todas as opções padrão.
   - Para confirmar que funcionou:
     ```
     git --version
     ```

3. **VS Code** (editor de código)
   - Acesse [code.visualstudio.com](https://code.visualstudio.com) e instale.

> **O que é o terminal?** É uma janela de texto onde você digita comandos. No Windows, procure por "Prompt de Comando" ou "PowerShell" no menu Iniciar. No VS Code, você pode abrir um terminal pelo menu **Terminal → New Terminal**.

---

### Passo 2 — Copie o repositório para o seu computador

Abra o terminal e execute os comandos abaixo um por vez, pressionando Enter após cada um:

```bash
git clone https://github.com/Lucas0liveira/fornecedores.git
cd fornecedores
```

> **O que é um repositório?** É uma pasta do projeto que tem todo o histórico de alterações salvas. O `git clone` baixa uma cópia completa do projeto.

---

### Passo 3 — Instale as dependências

Dentro da pasta do projeto, execute:

```bash
npm install
```

Isso pode demorar alguns minutos. Ele vai baixar todas as bibliotecas externas que o projeto usa.

---

### Passo 4 — Configure as variáveis de ambiente

O projeto precisa de credenciais para se conectar ao banco de dados. Essas informações **nunca devem ser compartilhadas publicamente**.

1. Na raiz do projeto, crie um arquivo chamado `.env.local`.
2. Cole o conteúdo abaixo dentro dele:

```env
NEXT_PUBLIC_SUPABASE_URL=sua_url_aqui
NEXT_PUBLIC_SUPABASE_ANON_KEY=sua_chave_aqui
```

3. Peça ao professor as credenciais corretas para preencher esses campos.

> **Por que não colocar no README?** Porque esse arquivo é público. Qualquer pessoa poderia acessar o banco de dados se as credenciais ficassem aqui. O arquivo `.env.local` fica apenas no seu computador e nunca é enviado ao GitHub (ele está no `.gitignore`).

---

### Passo 5 — Inicie o servidor de desenvolvimento

```bash
npm run dev
```

Abra o navegador em [http://localhost:3000](http://localhost:3000) — o site estará rodando localmente!

Para parar o servidor, pressione `Ctrl + C` no terminal.

---

## Como contribuir

Contribuir significa sugerir melhorias ou correções no código. O fluxo abaixo garante que o professor revise tudo antes de qualquer alteração ir ao ar.

### Fluxo completo (passo a passo)

#### 1. Faça um Fork do repositório

Um **fork** é uma cópia do projeto na **sua** conta do GitHub. Você edita a sua cópia sem mexer no original.

- Acesse o repositório no GitHub.
- Clique no botão **Fork** (canto superior direito).
- Clique em **Create fork**.

#### 2. Clone o seu fork

Substitua `SEU_USUARIO` pelo seu nome de usuário no GitHub:

```bash
git clone https://github.com/SEU_USUARIO/fornecedores.git
cd fornecedores
```

#### 3. Crie uma branch para a sua alteração

Uma **branch** é como uma linha do tempo paralela. Você faz suas mudanças nela sem afetar a versão principal.

```bash
git checkout -b minha-contribuicao
```

Dê um nome descritivo no lugar de `minha-contribuicao`. Exemplos:
- `correcao-typo-pagina-inicial`
- `adiciona-fornecedor-padaria`
- `melhora-layout-carrinho`

#### 4. Faça as alterações

Abra o projeto no VS Code (`code .`) e faça as suas mudanças.

#### 5. Salve as alterações no Git

Após editar os arquivos, execute:

```bash
git add .
git commit -m "Descreva o que você fez aqui"
```

O texto entre aspas depois de `-m` é a mensagem do commit — escreva em português e seja específico. Exemplos:
- `"Corrige erro de digitação na página inicial"`
- `"Adiciona descrição ao produto pão francês"`

#### 6. Envie para o GitHub

```bash
git push origin minha-contribuicao
```

#### 7. Abra um Pull Request

Um **Pull Request (PR)** é um pedido para que as suas alterações sejam incorporadas ao projeto original.

- Acesse o seu fork no GitHub.
- Clique no botão **Compare & pull request** (vai aparecer automaticamente).
- Preencha o título e descreva o que você fez e por quê.
- Clique em **Create pull request**.

#### 8. Aguarde a revisão

O professor vai analisar as suas alterações, pode pedir ajustes, e quando aprovar, vai integrar ao projeto. Você receberá uma notificação por e-mail.

---

### Regras de contribuição

- **Não altere** arquivos de configuração do banco de dados (`supabase/`) sem combinar antes com o professor.
- **Não inclua** arquivos `.env` ou senhas em nenhum commit.
- **Uma alteração por Pull Request** — PRs com muitas mudanças diferentes são mais difíceis de revisar.
- Escreva mensagens de commit em português e de forma clara.
- Se for uma dúvida ou sugestão que não é código, abra uma **Issue** em vez de um PR.

---

## Estrutura de pastas

```
fornecedores/
├── src/
│   ├── app/                  # Páginas do site (cada pasta = uma rota)
│   │   ├── page.tsx          # Página inicial (/)
│   │   ├── s/[id]/           # Catálogo do fornecedor (/s/123)
│   │   ├── cart/             # Carrinho (/cart)
│   │   ├── review/           # Revisão do pedido (/review)
│   │   ├── sent/             # Confirmação de envio (/sent)
│   │   └── admin/            # Área administrativa (/admin)
│   ├── components/           # Partes reutilizáveis da interface (cabeçalho, rodapé)
│   ├── lib/                  # Funções auxiliares e conexão com o banco
│   └── store/                # Gerenciamento do carrinho (Zustand)
├── supabase/                 # Scripts SQL do banco de dados
├── public/                   # Imagens e arquivos estáticos
└── .env.local                # Suas credenciais locais (NÃO vai ao GitHub)
```

---

## Dúvidas frequentes

**"Apareceu um erro vermelho no terminal, o que faço?"**
Leia a mensagem com calma. Geralmente ela diz exatamente o que está errado. Copie o texto do erro e cole numa Issue no GitHub, ou mostre ao professor.

**"Esqueci de criar uma branch e fiz as alterações direto no main."**
Execute os comandos abaixo para salvar suas mudanças numa branch sem perder nada:
```bash
git stash
git checkout -b minha-contribuicao
git stash pop
```

**"O `npm install` travou ou deu erro."**
Tente apagar a pasta `node_modules` e o arquivo `package-lock.json`, depois rode `npm install` novamente.

**"Não consigo acessar o site depois de rodar `npm run dev`."**
Verifique se o arquivo `.env.local` existe e se as credenciais foram preenchidas corretamente. Peça ajuda ao professor.

**"Como vejo as alterações que outros fizeram?"**
```bash
git pull origin main
```
Isso atualiza o seu repositório local com as mudanças mais recentes.

**"O que é uma Issue?"**
É um espaço no GitHub para reportar bugs, sugerir melhorias ou fazer perguntas. Acesse a aba **Issues** no repositório e clique em **New issue**.

---

## Licença

Este projeto é educacional e de uso restrito à turma. Consulte o professor antes de usar o código em outros contextos.
