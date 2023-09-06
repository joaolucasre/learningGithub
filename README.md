# Aprendendo a Versionar Seus Projetos com Git & Github

## Git

- Abra o terminal no VSCode
- selecione o programa do terminal (Git Bash)

### 1. Iniciar um repositório
- git init

### 2. Configurando o Git
- git congig --global
    2.1 name
    - git congig --global user.name "nome"
    2.2 email
    - git congig --global user.email "email@mail.com"
    2.3 validar se as configurações foram registradas
    - git config --list (se necessário aperte Enter até aparecer (END), em seguida aperte a tecla 'Q' para voltar pro master)

### 3. Adicionando arquivos
    3.1 Todos os arquivos
    - git add .
    3.2 Um arquivo específico (ex.: html)
    - git add index.html

### 4. Criando o Commit
* Commit é a versão do seu projeto. Na medida que você inclui novas informações, você vai adicionando commits no git, ou seja, versões atualizadas em uma linha do tempo.
    4.1 Adicionar mensagem
    - git commit -m "comentário sobre o commit"

### 5. Informações sobre os Commits criados
* Permite que eu veja todos os commits criados no projeto, com ou mais detalhes ou os ultimos x commits criados (x é a quantidade em número)
    5.1 Ver informações detalhadas do commit (id, autor, data e mensagem)
    - git log
    5.2 Ver informação resumida do commit em uma linha (id e mensagem)
    - git log --oneline
    5.3 Ver os x últimos commits criados (ex.: últimos 2 commits)
    - git log -n 2 

### 6. Estágios do arquivo (git status)
* Cada arquivo criado em um projeto passa por um caminho no git, segmentado em Working Directory, Stage Area e Repositório.
** Working Directory: é onde se encontram arquivos recém-criados ou modificados.
** Stage Area = após os arquivos serem adicionados no git (git add), se encontram nesse status
** Repository = Finalmente, os arquivos são commitados e passam a pertencer ao repositório.
    6.1 Git Status: comando para visualizar em que status está o arquivo.
    - git status

### 7. HEAD
* HEAD é a marcação que indica qual foi a última atualização do projeto, isto é, o último commit realizado. Ao executar o git log, conseguiremos ver qual é o commit mais atualizado pela demarcação HEAD, segue o exemplo:

```
$ git log
commit 8c954f82a462764b48a2d5352600a513eae72592 (HEAD -> master)
Author: joaolucasre <oliveirajoaolucasr@gmail.com>
Date:   Sun Sep 3 13:28:49 2023 -0300
```

### 8. Identificando as modificações feitas no arquivo
* ao realizar modificações em um arquivo, é possível visualizar qual foi exatamente a modificação realizada através do comando git diff
- git diff

### 9. Desfazendo modificações (ex.: index.html) de acordo com o status
* De acordo com o estágio do arquivo, é possível restaura-lo para o estágio anterior.
    9.1 Working Directory
    - git restore .
    9.2 Stage Area
    - git restore --staged .
    9.3 Corrigindo mensagem o útimo commit
    - git commit --amend -m "mensagem do commit corrigido"
    9.4 Desfazendo o último commit
    - git reset --soft HEAD~1


## Github

### 1. Configurando o SHH
- Veja as instruções no link: 
https://efficient-sloth-d85.notion.site/Configurando-SSH-f4996d82d1a242709b789fc7e12f41a7

### 2. Adicionando repositório no github
- Ao acessar sua conta no github, clique no sinal de '+' disponível no canto superior direito da página, em seguida, 'new repository'.
- Insira o nome do seu repositório e clique em 'create repository'
- Ao criar o repositório, siga as isntruções disponíveis para configurar o git.

### 3. Configurando o git
- para iniciar o repositório no git, siga as instruções disponíveis em 'Nivel 7/notes.md'
3.1: configurando a branch main
    - Em seguida configure a branch main, caso esteja na branch MASTER com o seguinte comando:
    git branch -M main
3.2: adicionando o repositório github através da chave SSH
    - Adicione a origem do seu repositório no github através do comando:
    git remote add origin git@github.com:joaolucasre/example.git
3.3: empurrando o repositório da main para o github
    - git push -u origin main

### 4. Git Push: Atualizando versões do repositório no Github
- Sempre que editar as informações do seu repositório, você poderá atualizar a versão no github através do passo a passo:
    git add .
    git commit -m "new atualization"
    git push

### 5. Gitignore
- Trata-se de um arquivo onde eu posso colocar pastas e/ou arquivos que eu não quero dar push no github.

### 6. Git Cached
- Caso eu dê push em uma pasta ou arquivo no github e depois pretendo tirar, isto é, colocar no .gitignore, eu dou um comando no git da seguinte forma:

    git rm -r --cached .

### 7. Gitkeep
-Ao contrário do gitignore, o gitkeep serve para preservar pastas sem conteúdo, com o intuito de mostrá-las no github. Sem o gitkeep, pastas vazias não aparecem. Para criar o gitkeep, basta criar uma pasta vazia e incluir o seguinte arquivo dentro dela:

    .gitkeep

### 8. Historico de Commits no Github
- Para visualizar o histórico de commits pushados para o github, basta no número de commits realizados na parte superior direita.

### 9. Git Clone
- O git clone serve para você continuar editando seu repositório de onde parou através de outra máquina. Dessa forma, não será necessário baixar o repositório do githib, apenas clonar e continuar sua edição. Atenção às instruções:
* 9.1: Copiar SSH do repositório
    Aqui você irá copiar o SSH do seu repositório no gtihub
* 9.2: Clonar o repositório no terminal git
    Em seguida irá digitar o seguinte comando:
        
        cd pasta/endereçodapastanamaquina (aqui você pode simplesmente digitar cd e arrastar a pasta onde quer continuar editando seu repositório)

        git clone git@github.com:joaolucasre/learningGithub.git (exemplo de ssh colado)
* 9.3 inclua o repositório clonado no vscode e continue a editar
    Por fim, você irá adicionar o repositório no vscode e continuar editando. Para atualizar as versões no github, basta seguir as instruções anteriores.

### 10. Git Pull
- Este comando serve para atualizar as edições feitas no seu repositório pelo github na sua máquina ou em outra que você esteja usando para continuar a realizar o seu projeto.
    * 10.1 Git Remote --v
        Este comando serve para você saber se o repositório está sincronizado com a máquina e o github. Se aparecer (fetch) e (push) nas duas linhas abaixo, respectivamente, está tudo certo.
    * 10.2 Edições feitas diretamente no github
        Caso você ou outra pessoa edite algum arquivo no repositório que você está trabalhando no github, use o git pull para sincronizar com a maquina.

### 11. README.md
- O README é um arquivo de documentação do seu projeto. Para que possa ser visualizado no github deve estar exatamente com esse nome. Lá você insere tudo o que você está fazendo ou aprendendo, visando facilitar o entendidmento de qualque pessoa que queira conhecer seus trabalhos no github.
- O README oide ser criado diretamente no worksplace do vcscode ou pelo github. A depender do caso, deve-se fazer um git push ou git pull respectivamente.