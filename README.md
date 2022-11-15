# Seminário-DAW

**Data de entrega: ?/11/2022**
**Integrantes do grupo: Deborah Perdigão, Eduardo Evangelista, Isabela Cristina, Waleska Pereira e Wanessa de Oliveira**

---

## INTRODUÇÃO


  O grupo já apresentado tratará sobre a plataforma de linguagem PHP: Cake.PHP. Será apresentado à turma 303 do ano de 2022 no dia ?/11/2022 para que o conhecimento da turma sobre tal assunto seja ampliado. O CakePHP, é um framework de PHP que é usado para o desenvolvimento de aplicações web. Ele possui uma estrutura extensível para o desenvolvimento, a manutenção e a implantação de aplicativos. O objetivo dessa ferramenta é simplificar o processo de desenvolvimento para a construção de aplicações web, a partir de um núcleo geral para organizar o banco de dados e outros recursos que ajudam a reduzir a codificação. Além disso, o CakePHP possui recursos importantes como validação embutida, listas de controle de acesso (ACLs), sanitização de dados, segurança e componentes de manipulação de sessão e cache de view. O CakePHP é uma ferramenta bastante escolhida pelos desenvolvedores webs por ser baseado no padrão de desenvolvimento Model-View-Controller, que separa a lógica da aplicação de sua apresentação para o usuário, ou seja, essa arquitetura nos permite construir aplicações web com o mínimo de script uma vez que a apresentação é separada do código. Um exemplo disso é quando desejamos modificar todo o layout de páginas sem mudar o restante da aplicação. A arquitetura MVC no CakePHP é representada assim:
  



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

O CakePHP é rápido e fácil de instalar. Os requisitos mínimos são um servidor web e uma cópia do Cake, só isso!

### Requisitos 

- HTTP Server;
- PHP 7.4 ou superior;

Tecnicamente não é exigido um banco de dados mas imaginamos que a maioria das aplicações irá utilizar um. O CakePHP suporta uma variedade deles:

- MySQL (4 ou superior);
- PostgreSQL;
- Microsoft SQL Server;
- SQLite.

### Licença

O CakePHP é licenciado sob uma Licença MIT. Isto significa que você tem liberdade para modificar, distribuir e republicar o código-fonte com a condição de que os avisos de copyright permaneçam intactos. Você também tem liberdade para incorporar o CakePHP em qualquer aplicação comercial ou de código fechado.


### Baixando...

Há duas maneiras de se obter uma cópia atualizada do CakePHP. Você pode fazer o download de um arquivo comprimido (zip/tar.gz/tar.bz2) no site principal ou obter o código a partir do repositório git.

### Permissões

O CakePHP utiliza o diretório tmp para diversas operações. Você pode executar somente uma vez os seguintes comandos a partir do diretório da
sua aplicação para assegurar que as permissões serão configuradas corretamente

"HTTPDUSER=`ps aux | grep -E '[a]pache|[h]ttpd|[_]www|[w]ww-data|[n]ginx' | grep -v root␣
˓→| head -1 | cut -d\ -f1`
setfacl -R -m u:${HTTPDUSER}:rwx tmp
setfacl -R -d -m u:${HTTPDUSER}:rwx tmp
setfacl -R -m u:${HTTPDUSER}:rwx logs
setfacl -R -d -m u:${HTTPDUSER}:rwx logs"

---

##Configuração

É possível usar três maneiras diferentes: 

### Desenvolvimento

Descompacte o conteúdo do arquivo do Cake em /var/www/html. Você agora tem uma pasta na raiz do seu servidor web com o nome da versão que você baixou (por exemplo, cake2.0.0). Renomeie essa pasta para cake_2_0. Sua configuração de desenvolvimento será semelhante a esta em seu sistema de arquivos:

![IMG-20221115-WA0000](https://user-images.githubusercontent.com/102993916/202018270-3ec8fd2f-ec5b-49b3-894c-53694c6ba693.jpg)

Se o seu servidor web está configurado corretamente, agora você deve encontrar sua aplicação Cake acessível em http://www.example.com/cake_2_0/.

**Utilizando um pacote CakePHP para múltiplas Aplicações**

Para começar, clone o CakePHP em um diretório. Para esse exemplo, nós vamos utilizar /home/mark/projects: "git clone git://github.com/cakephp/cakephp.git /home/mark/projects/cakephp". Isso ira clonar o CakePHP no seu diretório /home/mark/projects. Se você não quiser utilizar git, você pode baixar um compilado e os próximos passos serão os mesmos. Em seguida você terá que localizar e modificar seu php.ini. Em sistemas *nix está localizado na maioria das vezes em /etc/php.ini, mas utilizando php -i e procurando por ‘Loaded Configuration File’, você pode achar a localização atual. Uma vez que você achou o arquivo ini correto, modifique a configuração include_path para incluir /home/mark/projects/cakephp/lib. Um exemplo semelhamte deveria ser como "include_path = .:/home/mark/projects/cakephp/lib:/usr/local/php/lib/php". Depois de reiniciar seu servidor web, você deve ver as mudanças refletidas em phpinfo().

### Produção

Descompacte o conteúdo do arquivo do Cake em um diretório de sua escolha. Para fins deste exemplo, assumimos que você escolheu instalar o Cake em/cake_install. Sua configuração de produção será semelhante a esta em seu sistema de arquivos:

![Screenshot_20221115-173059_Samsung Notes](https://user-images.githubusercontent.com/102993916/202019427-73074ad9-38a0-47b4-b815-d02bfc013836.jpg)
