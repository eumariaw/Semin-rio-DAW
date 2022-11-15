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

## Configuração

É possível usar três maneiras diferentes: 

### Desenvolvimento

Descompacte o conteúdo do arquivo do Cake em /var/www/html. Você agora tem uma pasta na raiz do seu servidor web com o nome da versão que você baixou (por exemplo, cake2.0.0). Renomeie essa pasta para cake_2_0. Sua configuração de desenvolvimento será semelhante a esta em seu sistema de arquivos:

![IMG-20221115-WA0000](https://user-images.githubusercontent.com/102993916/202018270-3ec8fd2f-ec5b-49b3-894c-53694c6ba693.jpg)

Se o seu servidor web está configurado corretamente, agora você deve encontrar sua aplicação Cake acessível em http://www.example.com/cake_2_0/.

**Utilizando um pacote CakePHP para múltiplas Aplicações**

Para começar, clone o CakePHP em um diretório. 

Para esse exemplo, nós vamos utilizar /home/mark/projects: "git clone git://github.com/cakephp/cakephp.git /home/mark/projects/cakephp". 

Isso ira clonar o CakePHP no seu diretório /home/mark/projects. Se você não quiser utilizar git, você pode baixar um compilado e os próximos passos serão os mesmos.

Em seguida você terá que localizar e modificar seu php.ini. Em sistemas nix está localizado na maioria das vezes em /etc/php.ini, mas utilizando php -i e procurando por ‘Loaded Configuration File’, você pode achar a localização atual.

Uma vez que você achou o arquivo ini correto, modifique a configuração include_path para incluir /home/mark/projects/cakephp/lib. Um exemplo semelhamte deveria ser como "include_path = .:/home/mark/projects/cakephp/lib:/usr/local/php/lib/php". 

Depois de reiniciar seu servidor web, você deve ver as mudanças refletidas em phpinfo().

### Produção

Descompacte o conteúdo do arquivo do Cake em um diretório de sua escolha. Para fins deste exemplo, assumimos que você escolheu instalar o Cake em/cake_install. Sua configuração de produção será semelhante a esta em seu sistema de arquivos:

![Screenshot_20221115-173059_Samsung Notes](https://user-images.githubusercontent.com/102993916/202019427-73074ad9-38a0-47b4-b815-d02bfc013836.jpg)

Desenvolvedores usando o Apache devem definir o DocumentRoot do domínio para: "DocumentRoot /cake_install/app/webroot" Se o seu servidor web estiver configurado corretamente, você deve encontrar agora sua aplicação Cake acessível em http://www.example.com.

### Instalação Avançada e Configuração Específica por Servidor

**Instalação Avançada**

Pode haver algumas situações onde você deseja colocar os diretórios do CakePHP em diferentes locais no sistema de arquivos. Isto pode ser devido a uma restrição do servidor compartilhado, ou talvez você queira apenas que algumas aplicações compartilhem as bibliotecas do Cake.

Em primeiro lugar, note que há três partes principais de uma aplicação CakePHP.

1. As bibliotecas do núcleo do CakePHP, em /cake.
2. O código da sua aplicação, em /app.
3. Os arquivos públicos da sua aplicação, normalmente em /app/webroot.

Cada um desses diretórios podem ser localizados em qualquer em seu sistema de arquivos, com exceção do webroot, que precisa ser acessível pelo seu servidor web. Você pode até mesmo mover a pasta webroot para fora da pasta app, desde que você diga ao Cake onde você colocou. Para configurar sua instalação do Cake, você precisa fazer algumas modificações nos seguintes arquivos.

- /app/webroot/index.php
- /app/webroot/test.php

Há três constantes que você precisa editar: ROOT, APP_DIR, e CAKE_CORE_INCLUDE_PATH.

- ROOT deve ser configurada para o diretório que contém sua pasta app.
- APP_DIR deve ser definida como o nome de sua pasta app.
- CAKE_CORE_INCLUDE_PATH deve ser definida como o caminho da sua pasta de bibliotecas do CakePHP.

Dado este tipo de configuração, eu preciso editar meu arquivo webroot/index.php (que vai acabar em /var/www/mysite/index.php, neste exemplo) para algo como o seguinte:

![Screenshot_20221115-182541_Samsung Notes](https://user-images.githubusercontent.com/102993916/202028500-7642713d-087c-4f91-a5fb-c90e2529c660.jpg)

Recomenda-se a utilização da constante DS ao invés das barras para delimitar os caminhos de arquivos.

**Apache e mod_rewrite (e .htaccess)**

Aqui estão algumas coisas que você pode tentar fazer para rodar corretamente. Primeiro veja o seu httpd.conf.

1. Tenha certeza que a sobreposição do .htaccess está sendo permitida, ou seja, que o AllowOverride está configurado como All para o DocumentRoot. Você deve ver algo similar a isso:

![Screenshot_20221115-182847_Samsung Notes](https://user-images.githubusercontent.com/102993916/202032164-e510e2e3-3f83-4e11-9c9b-35a987f358d8.jpg)


2. Tenha certeza de estar carregando o mod_rewrite corretamente. Você deve ver algo como: "LoadModule rewrite_module libexec/apache2/mod_rewrite.so".

Depois de fazer as alterações, reinicie o Apache para ter certeza que as configurações estão aivas. Verifique se os seus arquivos .htaccess estão nos diretórios corretos.

3. Tenha certeza que sua cópia do CakePHP é veio da seção de downloads do nosso site ou do nosso repositório GIT, e foi descompactada corretamente verificando os seus arquivos .htaccess.

No diretório raiz do Cake (precisa ser copiado para o seu DocumentRoot, este redireciona tudo para a sua aplicação):

![Screenshot_20221115-183144_Samsung Notes](https://user-images.githubusercontent.com/102993916/202029524-dd2ffa9a-68a4-436a-bd5b-e78eaef0b08d.jpg)

O diretório app do seu Cake (será copiado para o diretório principal da sua aplicação pelo bake):

![Screenshot_20221115-183501_Samsung Notes](https://user-images.githubusercontent.com/102993916/202030034-2f6a3a0f-d364-48e1-90d1-de84dd19b55b.jpg)

Diretório webroot do Cake (será copiado para a raiz da sua aplicação web pelo bake):

![Screenshot_20221115-183625_Samsung Notes](https://user-images.githubusercontent.com/102993916/202032225-9c90d534-9004-4b7d-bd1a-51eb7becf94b.jpg)

**URLs amigáveis e Lighttpd**

Usando o mod_rewrite O modo mais fácil para se obter URLs amigáveis é adicionando este script na configuração do seu lighty. Basta editar a URL, e tudo deve funcionar. Por favor, note que isto não funciona em instalações do Cake em subdiretórios.

![Screenshot_20221115-183805_Samsung Notes](https://user-images.githubusercontent.com/102993916/202030572-700489b8-d8d1-4722-a7a6-5cb42aa2c185.jpg)

Usando o mod_magnet Para utiizar URLs amigáveis com o CakePHP e o Lighttpd, coloque este script LUA em /etc/lighttpd/cake.

![Screenshot_20221115-183844_Samsung Notes](https://user-images.githubusercontent.com/102993916/202030762-000ad597-279c-46e4-a572-61085165f206.jpg)

![Screenshot_20221115-183945_Samsung Notes](https://user-images.githubusercontent.com/102993916/202032296-54e6783b-d68b-4a0b-ae2b-7df7bb285d41.jpg)

![Screenshot_20221115-184046_Samsung Notes](https://user-images.githubusercontent.com/102993916/202030959-b48f4420-46eb-4b39-8e93-875f2d1a9fa6.jpg)

**URLs amigáveis no nginx**

nginx é um servidor popular que, como Lighttpd, usa menos recursos do sistema. O inconveniente é que não faz uso de arquivos .htaccess como o Apache e o Lighttpd, por isso é necessário criar as URLs reescritas na configuração site-available.

![Screenshot_20221115-184154_Samsung Notes](https://user-images.githubusercontent.com/102993916/202031183-4e1cc6d0-53d5-4f3e-ad31-03bd625f7109.jpg)

**URL Rewrites no IIS7 (Windows hosts)**

O IIS7 não suporta nativamente os arquivos .htaccess.

1. Use o Microsift Web Plataform Installer para instalar o URL Rewrite Module 2.0.
2. Crie um novo arquivo dentro de sua pasta do CakePHP, chamado web.config.
3. Usando o Notepad ou algum outro editor de XML, copie o seguinte código no seu novo arquivo web.config. . .

![Screenshot_20221115-184316_Samsung Notes](https://user-images.githubusercontent.com/102993916/202031787-4d8ebec4-dddc-4ff3-8390-c0e2b7bca7c6.jpg)

![Screenshot_20221115-184403_Samsung Notes](https://user-images.githubusercontent.com/102993916/202031815-663688be-3314-4919-a128-6cddc99e2381.jpg)


**Comece agora!**

Tudo bem, vamos ver o CakePHP em ação. Dependendo de qual configuração você adotou, você deve apontar seu

navegador para http://example.com/ ou http://example.com/cake_install/. Neste ponto, você verá a página padrão do

CakePHP e a mensagem do estado da configuração do seu banco de dados.

Parabéns! Você já está pronto para criar sua primeira aplicação CakePHP.
