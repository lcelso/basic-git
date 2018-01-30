# Comandos Básicos Git #

Guia inicial de como utilizar o git e situações que ocorrem no dia a dia.

### Configuração

As configurações do GIT são armazenadas no arquivo **.gitconfig**, no caminho ~/.gitconfig.

As configurações realizadas através dos comandos abaixo serão incluídas no arquivo citado acima.

##### Setar usuário
	git config --global user.name "João Silva"

##### Setar email
	git config --global user.email joao@gmail.com

##### Setar editor
	git config --global core.editor vim

##### Setar ferramenta de merge
	git config --global merge.tool code

##### Listar configurações
	git config --list

##### Gerando chave ssh
	ssh-keygen -t rsa -b 4096 -C "joao@gmail.com"

Irá aparecer: Enter a file in which to save the key," aperte Enter. Sua chave ssh será gerada no diretório padrão.

Irá aparecer: Enter passphrase (empty for no passphrase), aperte Enter 2 vezes.

Sua chave se encontra no diretório ~/.ssh/, arquivo será ~/.ssh/id_rsa.pub.


### Iniciando um Projeto

Crie a pasta do seu projeto e acesse ela.

##### Iniciando seu projeto com git
	git init

##### Verificar estado dos arquivos/diretórios
	git status

##### Adicionando um arquivo
Você pode propor mudanças (adicioná-las ao Index) usando

	git add <arquivo>
	git add <arquivo> <arquivo> <arquivo>
	git add . (Adiciona todos arquivos/diretórios)

##### Confirmando (Commitando) suas alterações
Agora o arquivo é enviado para o HEAD, mas ainda não esta no repositório remoto.

	git commit <meuarquivo> -m "minha mensagem de commit"
	git commit -v (Abre seu editor configurado, onde contém o diff das alterações realizadas,
	podendo criar sua mensagem)

##### Remover arquivo
	git rm meu_arquivo.txt

##### Remover diretório
	git rm -r diretorio

##### Exibir histórico
	git log

##### Exibir histórico com diff das alterações
	git log -p

##### Exibir histório de um arquivo específico
	git log -- <caminho_do_arquivo>

##### Exibir histório de um determinado autor
	git log --author=usuario


##### Desfazendo alteração local (working directory)
Este comando deve ser utilizando enquanto o arquivo não foi adicionado na **staged area**.

	git checkout -- <arquivo>

##### Desfazendo alteração local (staging area)
Este comando deve ser utilizando quando o arquivo já foi adicionado na **staged area**.

	git reset HEAD <arquivo>

A alteração do diretório pode ser realizada através do comando abaixo:
	git checkout <arquivo>

##### Criando uma branch a partir da branch atual

	git checkout -b <nome-da-branch>

##### Listando as branchs locais

	git branch

![Exemplo](https://github.com/lcelso/basic-git/blob/master/imagens/branch-local.png)

E ele te mostra a branch atual que você esta no momento com um * na frente dela

### Repositório Remoto
##### Exibir os repositórios remotos

	git remote -v

##### Vincular repositório local com um repositório remoto

	git remote add origin git@github.com:leocomelli/curso-git.git

##### Exibir informações dos repositórios remotos

	git remote show origin

##### Renomear um repositório remoto

	git remote rename origin curso-git

##### Desvincular um repositório remoto

	git remote rm curso-git

##### Enviar alterações para o repositório remoto
O primeiro push de um repositório deve conter o nome do repositório remoto e o branch.

	git push -u origin master

Os demais pushes não precisam dessa informação

	git push

##### Atualizar repositório local de acordo com o repositório remoto
Buscar as alterações, mas não aplica-las no branch atual

	git fecth

Atualizar os arquivos no branch atual

	git pull

##### Clonar um repositório remoto já existente

	git clone https://github.com/NodeRedis/node_redis.git

##### Listando as branchs remotas

	git branch --remote

##### Criar uma branch a partir da origin

	git checkout origin-feature-branch

![Exemplo](https://github.com/lcelso/basic-git/blob/master/imagens/branch-remote.png)

##### Apagar branch remota

	git push origin:nome-da-branch

### Referências

[Git Book](https://git-scm.com/book/pt-br/v2)

[Lista de comandos úteis do GIT](https://gist.github.com/leocomelli/2545add34e4fec21ec16)
