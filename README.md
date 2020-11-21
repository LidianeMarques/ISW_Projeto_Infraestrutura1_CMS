# <h1 align="center"> Infraestrutura para Sistemas Web <h1>
## <h2 align="center">Projeto em Infraestrutura 1 - CMS <h2>
  
  <div align="justify">
  
  <p>Esse projeto consiste na instalação de um: Content Management System, ou Sistema de Gestão de Conteúdos. Existem vários sistemas de CMS no mercado. Abordaremos o Wordpress.</p>   
  <p>Requisitos:</p>
  
  1. Você deverá instalar e configurar o Wordpress em sua infraestrutura; 
  2. Além da instalação e configuração, você deverá redigir um relatório descrevendo o processo;
  3. O relatório deverá ser escrito em Markdown e postado no seu GitHub, 
   a entrega consistem em mostrar o funcionamento do CMS e postar o link do relatório.
 
 <hr/>  
 
 ## 1. __Instalação do Wordpress no Ubuntu.__<h2>
  <h4>Pré-requisitos: </h4>
  <p> Para seguir este tutorial, será necessário ter acesso a um servidor Ubuntu 18.04 e realizar as seguintes tarefas antes de iniciar este guia: <p/>
  
  * __Criar um usuário sudo no seu servidor__: vamos realizar os passos neste guia usando um usuário não raiz com privilégios sudo. É possível criar um usuário com privilégios sudo seguindo nosso Guia de configuração inicial do servidor Ubuntu 18.04.
* __Instalar uma pilha LAMP:__ o WordPress precisará de um servidor Web, um banco de dados e um PHP para funcionar corretamente. Configurar uma pilha LAMP (Linux, Apache, MySQL, e PHP) cumpre todos esses requisitos. Siga este guia para instalar e configurar este software.
* __Proteger o seu site com o protocolo SSL:__ o Wordpress fornece conteúdo dinâmico e cuida da autenticação e autorização do usuário. O protocolo TLS/SSL é a tecnologia que permite criptografar o tráfego do seu site para que sua conexão esteja segura. A maneira como você irá configurar o SSL dependerá de se você tem um nome de domínio para seu site.
<br/>

### 1.1. Criando um banco de dados do MySQL para o WordPress  <h3>

  <p> O primeiro passo que vamos dar é um passo preparatório. O WordPress utiliza o MySQL para gerenciar e armazenar as informações do site e as do usuário. Já temos o MySQL instalado, mas precisamos criar um banco de dados e um usuário para o WordPress usar. </p>
<p> Para começar, faça login na conta raiz (administrativa) do MySQL, inserindo este comando: </p>

~~~shell
mysql -u root -p
~~~

  <p> Depois de executar o comando, será solicitada a senha que você configurou para a conta raiz do MySQL quando instalou o software. </p>

  <p>Primeiramente, criamos um banco de dados separado que o WordPress irá controlar. Você pode dar o nome que quiser ao banco de dados, mas neste tutorial nós o chamaremos de      wordpressdb para ficar mais simples. Crie o banco de dados para o WordPress digitando:</p>
  
~~~mysql
CREATE DATABASE wordpressdb DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;
~~~


>:information_source: __Nota:__ cada instrução do MySQL deve terminar em um ponto e vírgula (;). Verifique para garantir que a instrução foi seguida (ou seja, o ponto e vírgula foi usado), caso estiver enfrentando algum problema.

<p align="justify">Em seguida, vamos criar uma conta de usuário do MySQL separada que vamos usar exclusivamente para operar no nosso novo banco de dados. Criar bancos de dados e contas para uma função é uma boa ideia sob o ponto de vista de gerenciamento e segurança. Vamos usar o nome <b>wordpressuser</b> neste guia. Sinta-se à vontade para alterar isso se quiser.</p>

<p align="justify">Vamos criar essa conta, definir uma senha e conceder o acesso ao banco de dados que criamos. Podemos fazer isso digitando o seguinte comando: Lembre-se de escolher uma senha forte para o usuário do seu banco de dados:</p>

~~~mysql
CREATE USER 'wordpressuser'@'localhost' IDENTIFIED BY 'senha';
~~~

~~~mysql
GRANT ALL PRIVILEGES ON *.* TO 'wordpressuser'@'localhost' WITH GRANT OPTION;
~~~

<P>Agora, você tem um banco de dados e uma conta de usuário, criados especificamente para o WordPress. Precisamos atualizar os privilégios para que a instância atual do MySQL saiba sobre as alterações recentes que fizemos, para isso use o comando:</p>

~~~mysql
FLUSH PRIVILEGES;
~~~

<p>Depois de fazer todas essas configurações, saia do MySql digitando o comando:</p>

~~~mysql
EXIT;
~~~

<hr/>

### 1.2. Instalando extensões adicionais do PHP <h3>

<p>Ao configurar nossa pilha LAMP, precisamos apenas de um conjunto mínimo de extensões para fazer com que o PHP se comunique com o MySQL. O WordPress e muitos dos seus plug-ins potencializam extensões adicionais do PHP.</p>




</div>

