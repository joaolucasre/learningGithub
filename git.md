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