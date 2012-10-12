# Laravel Documentation

- [The Basics](#the-basics)
- [Who Will Enjoy Laravel?](#who-will-enjoy-laravel)
- [What Makes Laravel Different?](#laravel-is-different)
- [Application Structure](#application-structure)
- [Laravel's Community](#laravel-community)
- [License Information](#laravel-license)

<a name="the-basics"></a>
## O Básico

Bem vindo a documentação do Laravel. Estes documentos foram criados para um guia de iniciantes e como uma referência. Você pode acessar qualquer sessão e começar a aprender, recomendamos ler a documentação na ordem já definida pois nos permite estabelecer conceitos que serão usados documentos precedentes.

<a name="who-will-enjoy-laravel"></a>
## Quem vai gostar do Laravel?

Laravel é um framework que enfatiza flexibilidade e expressividade. Novos usuário irão encontrar a facilidade de desenvolver que é encontrada em outros frameworks PHP. Usuários mais experientes irão apreciar a oportunidade de modularizar os seus códigos de uma maneira que não é possíve em outros frameworks. A flexibilidade do Laravel permite a organização e modularização de sua aplicação ao longo do tempo quando for necessário e sua expressividade irá permitir a você e ao seu time, desenvolverem código que é conciso e fácil de ler.

<a name="laravel-is-different"></a>
## O que faz o Laravel diferente?

Existem várias maneiras em que o Laravel se difere de outros frameworks. Aqui estão alguns exemplos que achamos ser os principais:

- **Bundles** é o sistema modular do Laravel. [Repositório de Bundles](http://bundles.laravel.com/) já esta populado com uma boa quantidade de módulos que podem ser adicionados a sua aplicação facilmente. Você pode baixar o bundle pelo repositório ou utilizando o "Arisan" para instala-los automaticamente.
- **ORM Eloquent** é a implementação de ActiveRecord mais atualizada em PHP. Com a capacidade de aplicar constrints tanto em relações e eager-loading, você terá controle total sobre seus dados com toda a conveniência do ActiveRecord. Eloquente suporta, nativamente, todos os métodos da query-builder do Laravel, Fluent.
- **Lógica de Aplicação** pode ser implementada dentro de sua aplicação ou utilizando controllers (o que muitos desenvolvedores já estão familiarizados) ou diretamente dentro das declarações de rotas, usando uma sintaxe similar a do framework Sinatra. Laravel foi desenvolvido com a filosofia de dar ao desenvolvedor a flexibilidade que precisa para criar tudo, de um pequeno site a uma aplicação empresarial.
- **Reverse Routing** allows you to create links to named routes. When creating links just use the route's name and Laravel will automatically insert the correct URI.  This allows you to change your routes at a later time and Laravel will update all of the relevant links site-wide.
- **Restful Controllers** are an optional way to separate your GET and POST request logic. In a login example your controller's get_login() action would serve up the form and your controller's post_login() action would accept the posted form, validate, and either redirect to the login form with an error message or redirect your user to their dashboard.
- **Class Auto Loading** keeps you from having to maintain an autoloader configuration and from loading unnecessary components when they won't be used. Want to use a library or model?  Don't bother loading it, just use it. Laravel will handle the rest.
- **View Composers** are blocks of code that can be run when a view is loaded. A good example of this would be a blog side-navigation view that contains a list of random blog posts. Your composer would contain the logic to load the blog posts so that all you have to do i load the view and it's all ready for you. This keeps you from having to make sure that your controllers load the a bunch of data from your models for views that are unrelated to that method's page content.
- **The IoC container** (Inversion of Control) gives you a method for generating new objects and optionally instantiating and referencing singletons. IoC means that you'll rarely ever need to bootstrap any external libraries. It also means that you can access these objects from anywhere in your code without needing to deal with an inflexible monolithic structure. 
- **Migrations** are version control for your database schemas and they are directly integrated into Laravel. You can both generate and run migrations using the "Artisan" command-line utility. Once another member makes schema changes you can update your local copy from the repository and run migrations. Now you're up to date, too!
- **Unit-Testing** is an important part of Laravel. Laravel itself sports hundreds of tests to help ensure that new changes don't unexpectedly break anything. This is one of the reasons why Laravel is widely considered to have some of the most stable releases in the industry.  Laravel also makes it easy for you to write unit-tests for your own code.  You can then run tests with the "Artisan" command-line utility.
- **Automatic Pagination** prevents your application logic from being cluttered up with a bunch of pagination configuration. Instead of pulling in the current page, getting a count of db records, and selected your data using a limit/offset just call 'paginate' and tell Laravel where to output the paging links in your view. Laravel automatically does the rest. Laravel's pagination system was designed to be easy to implement and easy to change. It's also important to note that just because Laravel can handle these things automatically doesn't mean that you can't call and configure these systems manually if you prefer.

Estas são apenas algumas maneiras em que o Laravel se diferencia  de outros frameworks PHP. Todas estas características e muitas outras discutidas nesta documentação.

<a name="application-structure"></a>
## Estrutura da Aplicação

A estrutura de diretórios do Laravel foi desenvolvida para ser familiar para a maioria dos usuários de outros frameworks PHP. Aplicações web de qualquer forma ou tamanho podem ser criadas facilmente usanto esta estrutura similarmente a maneira você é criada em outros frameworks.

Contudo, devido a arquitetura única do Laravel, é possível para os desenvolvedores, criarem sua própria estrutura que é especialmente criada para sua aplicação. Isto pode ser benéfico para grandes projetos como CMS. Este tipo de flexibilidade é única do Laravel.

Em toda a documentação, vamos especificar os locais padrão para declarações, quando apropriado.

<a name="laravel-community"></a>
## Comunidade Laravel

Laravel tem sorte por ter apoio de uma comunidade entusiástica, amigável e crescente. Os [Forums](http://forums.laravel.com) são um ótimo lugar para encontrar ajuda, dar sugestões ou apenas ficar por dentro do que as pessoas estão dizendo.

Muitos de nós ficamos no IRC #larabel no FreeNode. [Here's a forum post explaining how you can join us.](http://forums.laravel.com/viewtopic.php?id=671) O canal é um ótimo lugar para aprender mais sobre desenvolvimento usando Laravel. Você é bem vindo para perguntar, responder as perguntas de outras pessoas ou apenas aprender com as perguntas e respostas. Nós amamos Laravel e gostariamos de falar sobre isto então não se sinta envergonhado!

<a name="laravel-license"></a>
## Informação de Licença

Laravel é software de código-aberto sob a licença [MIT](http://www.opensource.org/licenses/mit-license.php).