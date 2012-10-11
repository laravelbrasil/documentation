# Instalação e Configuração

## Conteúdo

- [Requerimentos](#requerimentos)
- [Instalação](#instalacao)
- [Configuração do servidor](#configuracao-do-servidor)
- [Configuração Básica](#configuracao-basica)
- [Ambientes](#ambientes)
- [URLs Limpas](#urls-limpas)

<a name="requerimentos"></a>
## Requerimentos

- Apache, nginx, ou outro servidor web compatível.
- Laravel aproveita os recursos mais poderosos do PHP 5.3. Consequentemente, PHP 5.3 é uma exigência.
- Laravel usa a [biblioteca FileInfo](http://php.net/manual/en/book.fileinfo.php) para detectar mime-types dos arquivos. Ela está incluído por padrão no PHP 5.3. No entanto, os usuários do Windows podem precisar adicionar uma linha ao seu arquivo php.ini antes do módulo Fileinfo estar ativado. Para mais informações confira os detalhes de [instalação / configuração no PHP.net](http://php.net/manual/en/fileinfo.installation.php).
- Laravel usa a [biblioteca Mcrypt](http://php.net/manual/en/book.mcrypt.php) para criptografia e gerar hash. Mcrypt normalmente vem pré-instalado. Se você não consegue encontrar Mcrypt na saída do phpinfo() verifique o site do fornecedor de sua instalação LAMP ou confira os detalhes de [instalação / configuração no PHP.net](http://php.net/manual/en/ book.mcrypt.php).

<a name="instalacao"></a>
## Instalação

1. [Download do Laravel](http://laravel.com/download)
2. Extraia o arquivo do Laravel e faça upload do seu conteúdo para seu servidor web.
3. Defina o valor da opção **key** no arquivo **config/application.php** com uma string de até 32 caracteres.
4. Verifique se a pasta 'storage/views' tem permissão para escrita.
5. Pronto, abra a sua aplicação em seu navegador.

Se tudo estiver bem, você verá a página inicial do Laravel. Prepare-se, há muito mais a aprender!

### Extras

Fazendo as seguintes instalações ajudará você tirar maior proveito do Laravel, mas elas não são necessárias:

- SQLite, MySQL, PostgreSQL, ou SQL Server PDO drivers.
- Memcached or APC.

### Problemas?

Caso você tenha problemas na instalação tente o seguinte:

- Verifique se o diretório **public** é a raiz do documento em seu servidor web. (veja: Configuração do Servidor)
- If you are using mod_rewrite, set the **index** option in **application/config/application.php** to an empty string.
- Se você estiver usando mod_rewrite, defina a opção **index** no arquivo **application/config/application.php** para uma string vazia.
- Verifique se a pasta **storage** e as subpastas tem permissão de escrita para o servidor web.

<a name="configuracao-do-servidor"></a>
## Configuração do Servidor

Como a maioria dos frameworks para web, Laravel é projetado para proteger seu código, bundles e armazenamento, colocando apenas os arquivos que são necessariamente públicos no DocumentRoot do servidor web. Isso evita que alguns tipos de erros de configuração do servidor faça com que o seu código (incluindo senhas de banco de dados e outros dados de configuração), se torne acessível através do servidor web. É melhor estar seguro.

In this example let's imagine that we installed Laravel to the directory **/Users/JonSnow/Sites/MySite**.
Neste exemplo, vamos imaginar que nós instalamos Laravel no diretório **/Users/JonSnow/Sites/MySite**.

Um exemplo muito simples de uma configuração VirtualHost do Apache para MySite pode ser assim.

	<VirtualHost *:80>
		DocumentRoot /Users/JonSnow/Sites/MySite/public
		ServerName mysite.dev
	</VirtualHost>

Note que, quando nós colocamos a linha **/Users/JonSnow/Sites/MySite** nosso DocumentRoot aponta para **/Users/JonSnow/Sites/MySite/public**.

Embora apontar o DocumentRoot para a pasta pública é uma boa práticas, é possível que você venha precisar usar o Laravel em um host que não permite que você altere seu DocumentRoot. Uma coleção de algoritmos para contornar essa necessidade pode ser encontrado no [fórum do Laravel.](Http://forums.laravel.com/viewtopic.php?id=1258)

<a name="configuracao-basica"></a>
## Configuração Básica

Toda a configuração fornecida está localizada na pasta config/ da sua aplicação. Recomendamos que você leia esses arquivos apenas para obter uma compreensão básica das opções disponíveis. Preste atenção especialmente no arquivo **application/config/application.php**, nele contém as opções de configuração básica para sua aplicação.

É **extremamente** importante que você altere a opção **application key** antes de trabalhar em seu site. Esta chave é usada em toda a estrutura para criptografia, hash, etc. Ela fica no arquivo **config/application.php** e deve ser colocado uma string aleatória de 32 caracteres. Uma chave pode ser gerada automaticamente usando o utilitário de linha de comando Artisan. Mais informações podem ser encontradas no [índice de comando do Artisan](/docs/artisan/commands).

> **Nota:** Se você estiver usando mod_rewrite, você deve definir a opção de index para uma string vazia.

<a name="ambientes"></a>
## Ambientes

Provavelmente, as opções de configuração que você precisa para o desenvolvimento local não é a mesmas que você precisa em seu servidor de produção. O padrão de manipulação de ambientes do Laravel é baseado em URL, o que torna a criação de ambientes muito fácil. Abra o arquivo 'paths.php' na raiz da sua instalação. Você deverá ver algo como isto:

	$environments = array(

		'local' => array('http://localhost*', '*.dev'),

	);

Isto diz ao Laravel que qualquer início de URLs com "localhost" ou terminando com ".dev" deve ser considerado parte do ambiente "local".

Em seguida, crie um diretório **application/config/local**. Todos os arquivos e opções que você colocar nesta pasta irá substituir as padrões no diretório **application/config**. Por exemplo, você pode criar um arquivo **application.php** dentro de seu novo diretório de configuração local:

	return array(

		'url' => 'http://localhost/laravel/public',

	);

Neste exemplo, a **URL** local irá substituir a opção **URL** do arquivo **application/config/application.php**. Observe que você só precisa especificar as opções que você deseja substituir.

Não é fácil? É claro, você é livre para desenvolver com vários ambientes configurados como desejar!

<a name="urls-limpas"></a>
## URLs Limpas

Provavelmente, você não quer que seu aplicativo contenha "index.php"nas URLs. Você pode removê-lo usando as regras de reescrita HTTP. Se você estiver usando o Apache para servir a sua aplicação, certifique-se de habilitar mod_rewrite e criar um arquivo **.htaccess** como este em seu diretório **public**:

	<IfModule mod_rewrite.c>
	     RewriteEngine on

	     RewriteCond %{REQUEST_FILENAME} !-f
	     RewriteCond %{REQUEST_FILENAME} !-d

	     RewriteRule ^(.*)$ index.php/$1 [L]
	</IfModule>

Se o ,htaccess acima não está funcionando para você tente este:

	Options +FollowSymLinks
	RewriteEngine on

	RewriteCond %{REQUEST_FILENAME} !-f
	RewriteCond %{REQUEST_FILENAME} !-d

	RewriteRule . index.php [L]

Depois de configurar o HTTP rewriting, você deve definir a opção **index** da configuração em **application/config/application.php** para uma string vazia.

> **Nota:** Cada servidor web tem um método diferente de fazer HTTP rewriting, e pode exigir um .htaccess diferente.