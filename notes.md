# Github

## 1. Configurando o SHH
- Veja as instruções no link: 
https://efficient-sloth-d85.notion.site/Configurando-SSH-f4996d82d1a242709b789fc7e12f41a7

## 2. Adicionando repositório no github
- Ao acessar sua conta no github, clique no sinal de '+' disponível no canto superior direito da página, em seguida, 'new repository'.
- Insira o nome do seu repositório e clique em 'create repository'
- Ao criar o repositório, siga as isntruções disponíveis para configurar o git.

## 3. Configurando o git
- para iniciar o repositório no git, siga as instruções disponíveis em 'Nivel 7/notes.md'
3.1: configurando a branch main
    - Em seguida configure a branch main, caso esteja na branch MASTER com o seguinte comando:
    git branch -M main
3.2: adicionando o repositório github através da chave SSH
    - Adicione a origem do seu repositório no github através do comando:
    git remote add origin git@github.com:joaolucasre/example.git
3.3: empurrando o repositório da main para o github
    - git push -u origin main

## 4. Atualizando versões do repositório no Github
- Sempre que editar as informações do seu repositório, você poderá atualizar a versão no github através do passo a passo:
    git add .
    git commit -m "new atualization"
    git push