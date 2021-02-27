
Comandos básicos: 

1. GIT CONFIG
Configurar o nome de usuário e endereço de e-mail. Isto é importante porque cada commit usa esta informação
ela é carimbada de forma imutável nos commits que você começa a criar

$ git config --global user.name "Fulano de Tal" // para o nome
$ git config --global user.email fulanodetal@exemplo.br // para o e-mail



2. GIT INIT
Para criar um novo repositório,  usar o comando git init. 
git init é um comando único que usamos durante a configuração inicial de um novo repositório. 
A execução desse comando cria um novo subdiretório .git no diretório de trabalho atual. 
Isso também cria um novo branch principal.

$git init

3. GIT ADD
O comando add é usado para adicionar qualquer alteração de arquivo ao INDEX (staged area) do git
que é uma área especial onde os arquivos estão sendo preparados para o commit.

Os principais sao: 

$git add *nome do arquivo + extensao*

$git add . //adiciona todos os arquivos

$git add *.txt (ou qqr outra extensao,vai adicionar todos os arquivos com essa extensao)


4. GIT COMMIT 
Fazendo Commit das Suas Alterações
Agora que sua área de stage está preparada do jeito que você quer, você pode fazer commit das suas alterações. 
Lembre-se que qualquer coisa que ainda não sido mandada para o stage — qualquer arquivo que você tenha criado ou 
alterado e que ainda não tenha sido adicionado com git add — não entrará nesse commit. 
Esses arquivos permanecerão no seu disco como arquivos alterados. 
Nesse caso, digamos que, da última vez que você executou git status, você viu que tudo estava no stage, 
então você está pronto para fazer commit de suas alterações. O jeito mais simples de fazer commit é digitar git commit:

$ git commit


Alternativamente, você pode digitar uma mensagem de commit diretamente na linha de comando, 
depois da opção -m do comando commit. Sempre necessário

$ git commit -m "Alteracao no readme.txt"


5. GIT IGNORE

Ignorando Arquivos

Arquivos que não quer que sejam adicionados automaticamente pelo Git e nem mesmo que ele os mostre como não-rastreados
Criamos um arquivo chamado .gitignore, contendo uma lista de padrões de nomes de arquivo que devem ser ignorados

# ignorar arquivos com extensão .a
*.a
# mas rastrear o arquivo lib.a, mesmo que você esteja ignorando os arquivos .a acima
!lib.a
# ignorar o arquivo TODO apenas no diretório atual, mas não em subdir/TODO
/TODO
# ignorar todos os arquivos no diretório build/
build/
# ignorar doc/notes.txt, mas não doc/server/arch.txt
doc/*.txt
# ignorar todos os arquivos .pdf no diretório doc/
doc/**/*.pdf

6. GIT ADD E GIT COMMIT 

Comando que adiciona e commita de uma vez só 

$ git commit -a -m "Mensagem das alteracoes"


6. Visualizando alteracoes

Exibe as alterações entre a árvore de trabalho, o índice ou uma árvore, as alterações entre o índice e uma árvore, 
as alterações entre as duas árvores, nas alterações resultantes de uma mesclagem, nas alterações entre dois objetos gota 
ou nas alterações entre dois arquivos no disco.

$ git diff

$ git diff --staged

-- LOG: Exibe os registros log do commit

$ git log

$ git log -p

(paginacao -enter e depois q)

$ gitk
(relatorio)


7. Reverter alteracoes

$git log --pretty=oneline

Exp. Dei um git add . mas nao quero que X arquivo seja commitado 

$ git reset HEAD {nomedoarquivo.ext}

Ex. Editei um arquivo e quero reverter as alteracoes
$ git checkout -- {nomedoarquivo.ext}


$ git rm {nomedoarquivo.ext}

8. Tags

São usadas para criar MARCAÇÕES nas versões diferentes de um sistema 
Ex. v0 v0.1 v1

$ git tag --listar tags existentes

$ git tag -a v1.0 -m "Versão 1.0" --criando a tag v1.0

--Comandos para criar uma tag em um commit antigo:

$ git log --pretty=oneline

$ git tag -a v0.0 {chave do commit} -m "Versão 0.0"

--Pronto! Tag criada em um commite antigo

$ git show v0.0 --traz os detalhes da criação da tag

--Caso eu queria acessar e modificar uma versão antiga

$ git checkout v0.0 -- acesso a versao antiga

$ git checkout v1.0


-- Caso queira deletar uma Tag

$git tag -d {nome da tag} 

9. Branchs

São as ramificações de um projeto

Em aplicações desenvolvidas por mais de uma pessoa, 
é uma boa prática que além da master, cada desenvolvedor crie e desenvolva seu código em sua própria branch, que pode ter qualquer nome.

A branch master é criada por padrão quando criamos um projeto no git.

-- Para criar um branch o comando é

$ git branch {nome da branch}

-- Para juntar as alteracoes entre as branchs 

$ git checkout master

$ git merge {nome da branch}

-- Para excluir uma branch 

$ git branch -d {nome da branch}

-- Checkout e criacao de branch em um unico comando

$ git checkout -b {nome da branch}

-- Commitando as alteracoes "

$ git commit -a -m "Correçao do bug fulano de tal

10. Clonando repositório remoto

O git clone é usado sobretudo para apontar para um repositório existente e fazer um clone ou cópia deste repositório no novo diretório, em outro local. 
O repositório original pode estar localizado no sistema de arquivos local ou em protocolos com suporte a acesso por máquinas remotas.

$ git clone {link do repositório remoto}

-- Pra enviar suas alteracoes pro repositorio remoto o comando é 

$ git remote --lista o nome do servidor remoto

-- pra enviar o seu projeto com as alteracoes usa o comando 

$ git push origin master --isso significa: git envie os arquivos para o origin que estao na master (minha branch)

-- para "atualizar" o projeto (pegar as modificaçoes dos outros desenvolvedores) usamos  o git pull

$ git pull origin master -- ta dizendo que eu quero puxar as alteracoes do origin para o meu master

-------------------------
GITHUB

1. Configuração inicial

Dar acesso a sua máquina local para que seja possível interagir com a conta git hub
Gerar chave SSH:

$ ssh-keygen

Essa chave ssh tem que ser incluída no seu perfil do GIT

