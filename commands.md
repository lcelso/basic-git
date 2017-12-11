# Comandos Básicos Git #

Guia inicial de como utilizar o git e situações que ocorrem no dia a dia.

## Configuração

### Geral

As configurações do GIT são armazenadas no arquivo **.gitconfig** localizado dentro do diretório do usuário do Sistema Operacional (Ex.: Windows: C:\Users\Documents and Settings\Leonardo ou *nix /home/leonardo).

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
