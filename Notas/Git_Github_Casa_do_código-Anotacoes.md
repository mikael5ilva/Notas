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