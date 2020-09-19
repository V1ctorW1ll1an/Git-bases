# Iniciar um repositorio git 
- git init 


# Reportar o estado do git no repositorio local
- git status 

# Untracked => significa que o arquivo foi criado, porém o git ainda não sabe de sua existencia

# Adicionar esse arquivo ao monitoramento do git 
- git add <nome do arquivo>

# Adicionar todos os arquivos criados ao monitoramento do git de uma vez 
# o ( . ) significa que é para adicionar todos os arquivos 
- git add . 

# Unstage => significa que o git já reconhece o arquivo e o mesmo já está pronto para ser versionando 

# Se modificarmos um arquivo ele será exibido com o status 
# Modified, o quer dizer que para nós versionarmos (commit) esse arquivo é preciso antes 
# adicionar novamente esse arquivo

# Com todos os arquivos ja adicionados, nós podemos criar o nosso commit 
# O commit informa ao git que o arquivo está pronto para ser versionado
# ou seja, o git já pode tirar o seu primeiro snapshot do arquivo
# O comando para o commit é bem simples 
# sendo que a flag [-m] indica que vc quer passar uma mensagem junto com o seu commit 
# deixando explicito o que foi modificado no arquivo 
- git commit -m "Mensagem"
- git commit -am "Mensagem" (so posso fazer isso com um arquivo que já é visto pelo git)

# Visualizar todos os commits ja feitos (os logs do git)
- git log 
- git log --decorate 
- git log --author="Victor"
- git shortlog
- git shortlog -sn
- git log --graph

# Mostrar informações de um commit 
- git show <hash do commit>

# Mostrar todos os dados que foram alterados 
- git log 

# Retornar o arquivo ao que ele era antes de qualquer alteração 
# esse comando so funciona se o arquivo nao tiver adicionado 
- git checkout <nome do arquivo>

# Caso o arquivo esteja adicionado é preciso fazer o reset para tira-lo do estado atual 
- git reset HEAD <nome do arquivo>

# Git reset (DANGER)

## Temos 3 flags para o git reset, sendo ela:

### --soft 
### --mixed 
### --hard 

## O --soft ele vai apenas apagar o commit, porem as modificações ainda estaram em staged prontas para um novo commit 
## geralmente usado quando vc quer apenas apagar os commits em si, porem nao quer perder o conteudo que foi adicionado em cada um 

## O --mixed faz a mesma coisa do soft porem ele volta os arquimos para o modo modified 

## O --hard reseta tudo o que foi feito no commit resetado


# Criar um repositorio global 

## Criar e adicionar um chave ssh 
 
# ssh conecta um usuario remoto ao servidor, tendo uma chave public do server, e a chave privado local que é a chave usada para abrir a chave remotamente 
[documentação do github para criar uma chave ssh](https://docs.github.com/pt/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)


# Conectando ao servidor remoto 
## Entendendo o git push e o git pull 
- git push -u origin <branch>
- git pull origin <branch>

### O -u é para fazer um save, para nao precisa digitar o origin novamente 
- git push

# Clonando um repositorio
- git clone <ssh ou https>

# Fazendo fork de projetos 
## Pegar um projeto que não é de nosso dominio e faço uma copia 
## ao contratio do clone, o git fork copia o repositorio criando assim um novo repositorio em um projeto 
## do dominio do usuario (quem fez o fork), muito util para fazer colaborações, corrigir bugs, entre outros, em 
## projetos que não são de nosso dominio, já que o clone não nos permite fazer push nos mesmos

# Criando branchs 
- git branch <nome da branch>

# Acessar a branch 
- git checkout <nome da branch>

# Criar e já acessar a branch instantaneamente 
- git checkout -b <nome da branch>

# Deletando branchs 
- git branch -D <nome da branch>

# Entendendo o merge entre branchs
## União entre duas branchs, deixa histórico linear, porem a estrutura fica quebrada
## (é possivel observar usando o git graph), e cria um novo commit unicamente para a finalidade de 
## juntar as duas branchs
- git merge <branch>

# Entendendo o rebase
## Monta um histórico quebrado, porem a estrutura fina linear, pois a brach é movida para o topo da branch 
## principal e não precisa criar uma branch extra para fazer a junção
- git rebase <branch>

# Entendendo o stash
## Guarda modificações que ainda nao foram commitadas
## muito util quando vc quer mudar de branch sem precisas commitar 
- git stash

## Aplicar as mudanças do git stash que estavam guardadas 
- git stash apply

## Listar as mudanças dentro do stash 
- git stash list

## Limpar as modificações dentro do stash 
- git stash clear

# Criando alias para os comandos 
## git config --global alias.<alias que vc deseja usar> <comando que vc quer vincular esse alias>

# Agrupando commits com as tags 
- git tag -a <versao> -m "mensagem"

## Subir as tags para o remoto 
- git push origin master --tags

# Revertendo dados sem perdo-los 
git revert <hash>

# Deletando tags 
- git tag -d <versao>
	
# Deletando tags e branchs remotamente
- git push origin :<versao da tag>
- git push origin :<nome da branch>
