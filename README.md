# laravel11x-project - Projeto para Estudo e Testes

## Este é um projeto completo que estou desenvolvendo em Laravel 11x para estudos, referências, treino e testes gerais. Espero que ele possa ajudar outros programadores.

## Configuração do ambiente de desenvolvimento.

Para este projeto, utilizei os seguintes aplicativos:

-   **Laragon** para PHP 8.3 e MySQL.
-   **VSCode** como IDE de desenvolvimento.
-   **DBeaver** para gerenciar o banco de dados graficamente.
-   **Laravel 11x** como framework de desenvolvimento PHP.

---

## Composer e Laravel 11x

Primeiramente instalei o **Composer** para fazer o gerenciamento das dependências do Laravel.

O Composer pode ser baixado em:

> [Baixe o Composer aqui...](https://getcomposer.org/download/)

Após instalar o Composer, verifique se ele foi adicionado nas _Variáveis de Ambiente_ do sistema operacional.

A seguir, no terminal de comandos, verifique se o Composer foi reconhecido.

```
composer -v
```

---

## Criando o projeto com Laravel 11x

Para criar o projeto em Laravel 11x, acesse o site da documentação.

Para criar o novo projeto:

```
composer create-project laravel/laravel:^11.0 laravel11x-project
```

> _Caso através deste comando ocorra erro no final da criação do projeto, pode ser por que agora o Laravel 11x já cria um novo projeto parametrizado para utilizar SQLite. Se você não tem o SQLite na máquina, receberá um erro como retorno._

Para evitar esse erro e já criar um novo projeto para usar o MySQL como banco de dados, execute os passos a seguir:

## Instalar o Composer/Laravel como global no computador de desenvolvendo.

```
composer global require laravel/installer
```

> _O comando composer global require laravel/installer é utilizado para instalar o instalador do Laravel de forma global no seu sistema. Isso permite que você crie novos projetos Laravel de maneira simplificada, utilizando o comando laravel new nome-do-projeto._

Verifique a versão do Laravel Installer para garantir que é a 5.1 ou superior:

```
laravel --version
```

Se a versão for inferior à 5.1, atualize o Laravel Installer:

```
composer global update laravel/installer
```

## Crie um novo projeto Laravel especificando o uso do MySQL:

```
laravel new nome-do-projeto --database=mysql
```

Após a criação do projeto, configure as credenciais do banco de dados no arquivo `.env` do seu projeto:

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nome_do_banco
DB_USERNAME=seu_usuario
DB_PASSWORD=sua_senha
```

A seguir, execute as migrates:

```
php artisan migrate
```

## Após a criação do projeto, parametrizar o arquivo `.env`:

```
APP_NAME=Laravel11x-Project
APP_DEBUG=true
APP_TIMEZONE=America/Belem
APP_URL=http://localhost:8000/

APP_LOCALE=pt-BR

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel11x_project
DB_USERNAME=root
DB_PASSWORD=123456
```

Em princípio, configure estas linhas dentro do arquivo `.env`

> Para saber qual o timezone correto de sua regição, use o seguinte link: [Lista de TimeZone para seu projeto...](https://www.php.net/manual/pt_BR/timezones.php)

## Após os ajustes, execute o projeto no navegador

Para rodar o servidor local do Laravel, execute o seguinte comando no terminal:

```
php artisan serve
```

A seguir, entre a url no navegador:

> [http://localhost:8000/](http://localhost:8000/)

> **OBS.:** é esperado que o arquivo `.env` não seja incluído quando você clona um repositório Laravel. O arquivo .env contém configurações sensíveis, como credenciais de banco de dados, chaves de API e outras variáveis de ambiente importantes que não devem ser compartilhadas publicamente no repositório.Por que o arquivo .env não é clonado? O Laravel (e outras boas práticas de desenvolvimento) adiciona o arquivo .env ao .gitignore, o que significa que ele é ignorado pelo Git. Isso impede que informações confidenciais ou específicas de cada ambiente de desenvolvimento sejam enviadas para o repositório e compartilhadas inadvertidamente.

## O que fazer após clonar o repositório do Laravel?

Após baixar o projeto para a máquina de desenvolvimento, abra o arquivo `.env.example` e salve como `.env` na pasta raiz do projeto. Esse será o novo arquivo de configurações do projeto na sua máquina.

Faça as configurações padrão conforme já foi mostrado acima.

### Gere a chave da aplicação.

O Laravel usa uma chave de aplicação que é gerada automaticamente no momento da instalação. Se você clonou o repositório e criou o arquivo .env, execute o comando abaixo para gerar essa chave:

```
php artisan key:generate
```

### Instale as dependências do projeto.

Faça a instalação das dependências do Laravel usando o Composer:

```
composer install
```

### Execute as migrations:

Rodar as migrations para criar as tabelas necessárias no banco de dados. Caso o banco ainda não existe, será perguntado se deseja criar o mesmo:

```
php artisan migrate
```

Com isso, o projeto está pronto para uso no computador de desenvolvimento.
