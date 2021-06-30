# Modelo Relacional :computer:

## Tabelas 

* Conjunto de dados dispostos em colunas e linhas referentes a um objetivo comum.
* As colunas são consideradas como "campos da tabela", como atributos da tabela.
* As linhas de uma tabela são chamadas também de tuplas, e é onde estão contidos os valores, os dados.


## O que pode ser definido como tabelas?
* Coisas tangíveis - Elementos físicos(carro, produto, animal)
* Funções - Perfis de usuário, status de compra
* Eventos ou ocorrências - Produtos de um pedido histórico de dados

## Colunas importantes

#### Chave Primária / Primary Key / PK

* Conjunto de um ou mais campos que nunca se repetem. Identidade da tabela. São utilizados como índice de referência na criação de relacionamentos entre tabelas.

### Chave Estrangeira / Foreign Key / FK

* Valor de referência a uma pk de outra tabela, ou da mesma tabela para criar um relacionamento.

## Sistema de Gerenciamento de banco de dados(SGBD)

* Conjunto de programas ou softwares responsáveis pelo gerenciamento de um banco de dados.
* Programas que Facilitam a administração do banco de dados.
* Ex: Oracle, MySQL, SQLServer, mongoDB etc.

## Introdução ao POSTGRESQL

* o que é ? SGBD
* Teve inicio no Departamento de Ciência da Computação na Universidade da Califórnia em Berkeley em 1986.
* SGBD Open source.

* MultProcessos
* Modelo Cliente/Servidor
* Point in time recovery (capacidade de restaurar)
* Linguagem procedural com suporte a várias limguagens de programação(perl, python, etc).
* Views, Functions, Procedures, Triggers.
* Consultas Complexas e Common table expressions(CTE)
* Suporte a dados geográficos(PostGIS)
* Controle de concorrência multi-versão.

## Melhores praticas

* Arquivo postgresql.conf -> 
	- Onde estão definidas todas as configurações di servidor postgreSQL.
	- Alguns parâmetros só podem se alterados com uma reinicialização do banco de dados.
	- A view pg_settings acessada por dentro do banco de dados, guarda todas as configurações atuais:
		 - SELECT name, setting
		 - FROM pg_settings;
	- Que é possivel usar o comando:
		 - SHOW [Parâmetro];

* O arquivo postgresql.conf
	- Por padrão, encontra-se dentro do diretório PGDATA definido no momento da inicialização do cluster de banco de dados.
	- No sistema operacional Ubunto, se o PostgreSQL foi instalado a partir do repositório oficial, o local do arquivo será diferente do diretório de dados.
	- /etc/postgresql/[versão]/[nome do cluster]/postgresql.conf


* Configurações de conexão no postgresql.conf
	- LISTEN_ADDRESS
		- Endereço(s) TCP/IP das interfaces que o servidor PostgreSQL vai escutar/liberar conexões.
	- PORT
		- A porta TCP que o servidor PostgreSQL vai ouvir. O padrão é 5432.
	- MAX_CONNECTIONS
		- Número máximo de conexões simultâneas no servidor PostgreSQL.
	- SUPERUSER_RESERVED_CONNECTIONS
		- Número de conexões (slots) reservadas para conexões ao banco de dados de super usuários.

* Configuração de autenticação
	- AUTHENTICATION_TIMEOUT
		- Tempo máximo em segundos para o cliente conseguir uma conexão com o servidor.
	- PASSWORD_ENCRYPTION
		- Algoritimo de criptografia das senhas dos novos usuários criados no banco de dados.
	- SSL
		- Habilita a conexão Criptografada por SSL(somente se o postgre foi compilado com suporte SSL).
