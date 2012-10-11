# Comandos do Artisan

## Conteúdo

- [Ajuda](#help)
- [Configuração da Aplicação](#application-configuration)
- [Sessões](#sessions)
- [Migrações](#migrations)
- [Pacotes](#bundles)
- [Tarefas](#tasks)
- [Testes Unitários](#unit-tests)
- [Roteamento](#routing)
- [Chaves da Aplicação](#keys)
- [Opções da ILC](#cli-options)

<a name="help"></a>
## Ajuda

Descrição  | Comando
------------- | -------------
Veja uma lista de comandos do artisan. | `php artisan help:commands`

<a name="application-configuration"></a>
## Configuração da Aplicação <small>[(Mais Informações)](/docs/install#basic-configuration)</small>

Descrição  | Comando
------------- | -------------
Gera uma chave de aplicação segura. Uma chave de aplicação não será gerada a não ser que o campo em **config/application.php** esteja vazio. | `php artisan key:generate`

<a name="sessions"></a>
## Sessões de Banco de Dados <small>[(Mais Informações)](/docs/session/config#database)</small>

Descrição  | Comando
------------- | -------------
Crie uma tabela de sessão  | `php artisan session:table`

<a name="migrations"></a>
## Migrações <small>[(Mais Informações)](/docs/database/migrations)</small>

Descrição  | Comando
------------- | -------------
Cria a tabela de migraçãoes do Laravel  | `php artisan migrate:install`
Criando uma migração  | `php artisan migrate:make create_users_table`
Criando uma migração para um pacote  |  `php artisan migrate:make bundle::tablename`
Running outstanding migrations  |  `php artisan migrate`
Running outstanding migrations in the application |  `php artisan migrate application`
Running all outstanding migrations in a bundle  |  `php artisan migrate bundle`
Desfazendo a última operação de migração | `php artisan migrate:rollback`
Desfazendo todas as migrações que já foram executadas alguma vez  |  `php artisan migrate:reset`

<a name="bundles"></a>
## Pacotes <small>[(Mais Informações)](/docs/bundles)</small>

Descrição  | Comando
------------- | -------------
Instala um pacote  |  `php artisan bundle:install eloquent`
Atualiza um pacote  |  `php artisan bundle:upgrade eloquent`
Atualiza todos os pacotes | `php artisan bundle:upgrade`
Publish a bundle assets | `php artisan bundle:publish bundle_name`
Publish all bundles assets | `php artisan bundle:publish`

<br>
> **Nota:** Após a instalação você precisa [registrar o pacote](../bundles/#registering-bundles)

<a name="tasks"></a>
## Taredas <small>[(Mais Informações)](/docs/artisan/tasks)</small>

Descrição  | Comando
------------- | -------------
Chamando uma tarefa  |  `php artisan notify`
Chamando uma tarefa e passando argumentos  |  `php artisan notify taylor`
Chamando um método específico em uma tarefa  |  `php artisan notify:urgent`
Rodando uma uma tarefa em um pacote | `php artisan admin::generate`
Rodando um métdo específico em um pacote  |  `php artisan admin::generate:list`

<a name="unit-tests"></a>
## Testes Unitários <small>[(Mais Informações)](/docs/testing)</small>

Descrição  | Comando
------------- | -------------
Rodando os testes da aplicação  |  `php artisan test`
Rodando os testes do pacote  |  `php artisan test bundle-name`

<a name="routing"></a>
## Roteando <small>[(Mais Informações)](/docs/routing)</small>

Descrição  | Comando
------------- | -------------
Chamando uma rota  |  `php artisan route:call get api/user/1`

<br>
> **Nota:** Você pode substituir get por post, put, delete, etc. 

<a name="keys"></a>
## Chaves da Aplicação

Descrição  | Comando
------------- | -------------
Gera uma chave da aplicação  |  `php artisan key:generate`

<br>
> **Nota:** Você pode especificar um tamanho alternativo para a chave adicionando um argumento extra ao comando.

<a name="cli-options"></a>
## Opções do ILC

Descrição  | Comando
------------- | -------------
Configurando o ambiente do Laravel  |  `php artisan foo --env=local`
Cofigurando a conexão padrão do banco de dados  |  `php artisan foo --database=sqlitename`
