# Seminário-DAW

**Data de entrega: ?/11/2022**
**Integrantes do grupo: Deborah Perdigão, Eduardo Evangelista, Isabela Cristina, Waleska Pereira e Wanessa de Oliveira**

---

## INTRODUÇÃO


  O grupo já apresentado tratará sobre a plataforma de linguagem PHP: Cake.PHP. Será apresentado à turma 303 do ano de 2022 no dia ?/11/2022 para que o conhecimento da turma sobre tal assunto seja ampliado.

  Imagine que você é um mero mortal e não sabe programar em PHP. Caso vocẽ não tenha um bom professor como a turma 303 do ano de 2022 do Colégio Técnico da UFMG acaba se tornando complicado. Ou até mesmo caso você não tenha tempo o suficiente ou o interesse necessário para aprender vocÊ pode usar o Cake.PHP para isso! 
 
  É possível criar blogs pessoais e muito mais! Essa é uma plataforma de criação de aplicações web, no qual o principal objetivo é permitir que você trabalhe em uma estrutura que possa programar de forma rápida e sem a perda de flexibilidade.

Caso você queira criar um blog é simples, rápido e fácil.

**Criando um blog com Cake.PHP**

Básico:
- Você precisará de um servidor web em funcionamento, um servidor de banco de dados e por último um conhecimento básico sobre PHP(é possível adiquir em pouquíssimo tempo com aulas gratuitas);
- Primeiro é necessário a instalação e configuração do Cake.php (está no próximo tópico);
- Logo após será preciso que se crie um banco de dados para gerenciar as postagens do seu blog.;
- Com o banco de dados criados é feita a criação da tabela;
- Configure em seguida o seu banco de dados;
- Cria-se o model;
- Cria-se o controller;
- Cria-se as as views;
- Adiciona-se e valida-se os artigos;
- Pode-se também editá-los e deletá-los.

Com o mais avançado você pode:
- Criar uma arvore de Categoria;
- Aprender a Migração de Plugin;
- Modificar as Tabelas;
- Gerar código esqueleto por categorias;
- Anexar árvore de compartamento para CategoriesTable;
- Reordenar categorias com TreeBahavior;
- Modificar o ArticlesController;
- Modificar os artigos Templatesr.

Autenticação e Autorização do seu blog:
- Cria-se todo o código relacionado ao Usuário;
- Autenticar com login e logout;
- Autorizar as pessoas permitidas.


---

## Instalação e configuração

Agora você aprenderá a instalar o Cake.PHP


### Requisitos necessários para instalação:

- HTTP Server;
- PHP 7.4 ou superior;
- extensão mbstring;
- extensão intl.


### Instalando...

Primeiramente, você precisará baixar e instalar o Composer execiutando "curl -s https://getcomposer.org/installer | php" no seu terminal, ou você pode baixar composer.phar do Site oficial do Composer. Para criar um novo app com Cake.PHP, basta executar "php composer.phar create-project --prefer-dist cakephp/app:4.* [app_name]"


**Mantendo sincronização com as últimas alterações no CakePHP**

Para se manter atualizado basta adicionar um "composer.json" em sua aplicação 
""require": {
  "cakephp/cakephp": "dev-master"
}"


**Permissões**

O CakePHP utiliza o diretório tmp para diversas operações. Você pode executar somente uma vez os seguintes comandos a partir do diretório da
sua aplicação para assegurar que as permissões serão configuradas corretamente

"HTTPDUSER=`ps aux | grep -E '[a]pache|[h]ttpd|[_]www|[w]ww-data|[n]ginx' | grep -v root␣
˓→| head -1 | cut -d\ -f1`
setfacl -R -m u:${HTTPDUSER}:rwx tmp
setfacl -R -d -m u:${HTTPDUSER}:rwx tmp
setfacl -R -m u:${HTTPDUSER}:rwx logs
setfacl -R -d -m u:${HTTPDUSER}:rwx logs"


**Servidor de Desenvolvimento**

para executar o servidor integrado do PHP que vai tornar sua aplicação disponível em ttp://host:port. A partir do console CakePHP da aplicação, execute: "bin/cake.server".
