# Livro Git/Github Casa do código - Anotações

## Instalação Linux
 * Utilizando uma distro Debian based, usando apt-get
    
    `$ sudo apt-get install git-all`

## Instalação Windows
 * Baixe diretamente do site oficial
  
   <https://git-scm.com/download/win>

---

## Configurações básicas
 * Identificar o Git com seu nome e email
  
   `$ git config --global user.name "Fulano da Silva`

   `$ git config --global user.email fulanodasilva.git@gmail.com`

---

## Criar um repositorio
 1. Crie uma pasta pessoal
 2. Abra a pasta pessoal que você criou e digite:

     `$ git init`
 > Sendo seu primeiro repositorio iniciado, é provável que apareça uma mensagem tipo: 
  `Initialized empty Git repository in /home/fulano/citacoes/.git/`

  3. Seu projeto agora é um repositório Git vazio. :ballot_box_with_check:
   
---
## Rastrear o arquivo
 Para ver a situação atual dos arquivos do repositório você usará o comando: 

`$ git status`

> Se o repositório estiver vazio desde sua criação, provavelmente aparecerá a mensagem:
>
>``` 
>#On branch master
>#
>#No commits yet
>#
>#nothing to commit (create/copy files and use "git add" to track)
>```
>Mostrando que não há arquivos para serem rastreados.

> Se você houver criando junto com um arquivo, é provável que saia algo como:
>```
># On branch master
>#
># Initial commit
>#
># Untracked files:
># (use "git add <file>..." to include in what will be committed)
>#
># arquivo.txt nothing added to commit but untracked files present (use "git add" to track)
>```
> Significa que o arquivo ainda não está sendo rastreado. Para que seja rastreado, vamos utilizar o comando:
> 
> `$ Git add arquivo.txt `
> 
> Dessa forma, se usarmos o comando `$ Git status` teremos a saída:
> 
> ```
> # On branch master
>#
>#Initial commit
>#
>#Changes to be committed:
>#(use "git rm --cached <file>..." to unstage)
>#
>#new file: arquivo.txt
>```
---

## Gravando o arquivo no repositório
Mais conhecido como _"Commitar"_, para gravarmos o arquivo no repositório usamos o comando:
` $ Git commit -m "citação do comentario"`

Observe que foi invocado o comando git commit, com a opção -m
para informar a mensagem do commit.

Deve aparecer algo dessa forma:

>[master (root-commit) 8666888] citação do comentario
>
>1 file changed, 2 insertions(+)
>
>create mode 100111 arquivo.txt

Se executarmos o comando `$ Git status` novamente, teremos a seguindo saída:
> On branch master
>
>nothing to commit, working directory clean
---

## Alterando o arquivo
Após digitar uma nova linha no arquivo, adicionar mais arquivos no repositório, fazer alterações dentro do projeto e rodarmos o comando `$ Git status` podemos observar que vai haver mudanças para serem rastreadas: 
>#On branch master
>
>#Changes not staged for commit:
>
>#(use "git add <"file">..." to update what will be committed)
>
>#(use "git checkout -- <"file">..." to discard changes in working directory)
>
>#modified: filmes.txt
>
>no changes added to commit (use "git add" and/or
>"git commit -a")

## Rastreando a gravando as alterações no repositório
Para rastrear a modificação, devemos usar o comando `$ Git add` novamente:

`$ Git add arquivo.txt`

Com a modificação rastreada, podemos agora gravá-la (commitar) no repositório com o comando `$ Git commit`:

`$ Git commit -m "citação do comentario 2"`

Devemos ter uma resposta semelhante a:
>
>[master 7878787] citação do comentario 2
>
>1 file changed, 1 insertion(+)
---

## Verificando alterações realizadas
Para verificar o histórico das alterações gravadas no repositório, podemos
executar o comando `$ git log`:

A saída será parecida com:

>commit 7878787000000000000000000000000000000000
>
>Author: Fulano da Silva <fulanodasilva.git@gmail.com>
>
>Date: Fri Apr 11 21:21:31 2014 -0300
>
>     Inserindo nova citacao
>
>commit 8666888000000000000000000000000000000000
>
>Author: Fulano da Silva <fulanodasilva.git@gmail.com>
>
>Date: Fri Apr 11 21:21:31 2014 -0300
>
>     Arquivo inicial de citacoes
---

## Compartilhando seu código atrávez do GitHub
Acesse o site <https://github.com/> e crie sua conta com nome, email e senha.

## Criando o repositório no GitHub
1. Clique no botão _New repository_.
2. No _repository name_ adicione um nome para o projeto remoto.
3. _Create repository_.

## Apontar o projeto para o GitHub
No terminal, certifique-se de estar no diretório onde está o repositório local.

Então, execute o comando: `$ git remote add origin https://github.com/fulanodasilva/repositorio.git`
>Não esquecer de alterar o "fulanodasilva" para o seu usuário GitHub.

## Enviar alterações para o GitHub
Com o repositório remoto configurado, poderá então enviar as mudanças para o GitHub.

Basta usar o comando `$ Git push origin master`. Com esse comando,enviamos as alterações para o repositório remoto configurado com o nome origin.
>Forneça seu usuário e senha do GitHub quando solicitado. Deverá aparecer algo semelhante à seguinte saída:
>
>Username for ’https://github.com’: fulanodasilva
>
>Password for ’https://fulanodasilva@github.com’:Counting objects: 6, done.
>
>Delta compression using up to 4 threads.
>
>Compressing objects: 100% (4/4), done.
>
>Writing objects: 100% (6/6), 609 bytes | 0 bytes/s, done.
>
>Total 6 (delta 1), reused 0 (delta 0)
>
>To https://github.com/fulanodasilva/citacoes.git
>
>*[new branch] master -> master