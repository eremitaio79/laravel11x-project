# Laravel11x-project

Projeto completo desenvolvido em Laravel 11.x para estudos, referências e testes. Este repositório serve como um guia prático e pode ajudar outros desenvolvedores em seus projetos.

## 🛠 Ambiente de Desenvolvimento

- **Laragon** - Servidor local com PHP 8.3 e MySQL
- **VSCode** - IDE de desenvolvimento
- **DBeaver** - Gerenciador gráfico de banco de dados
- **Laravel 11.x** - Framework PHP

## 📦 Pré-requisitos

### Composer

1. Instale o Composer através do [site oficial](https://getcomposer.org/download/)
2. Verifique se está nas variáveis de ambiente do sistema
3. Confirme a instalação:
   ```bash
   composer -v
   ```

### Laravel Installer

1. Instale o Laravel globalmente:
   ```bash
   composer global require laravel/installer
   ```

2. Verifique a versão (deve ser 5.1 ou superior):
   ```bash
   laravel --version
   ```

3. Se necessário, atualize o instalador:
   ```bash
   composer global update laravel/installer
   ```

## 🚀 Criando um Novo Projeto

### Método 1: Via Composer
```bash
composer create-project laravel/laravel:^11.0 laravel11x-project
```

### Método 2: Via Laravel Installer (Recomendado)
```bash
laravel new laravel11x-project --database=mysql
```

## ⚙️ Configuração

### 1. Configurar o arquivo .env
```env
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

> 📝 Para encontrar o timezone correto da sua região, consulte a [lista oficial de TimeZones do PHP](https://www.php.net/manual/pt_BR/timezones.php)

### 2. Iniciar o servidor
```bash
php artisan serve
```
Acesse: [http://localhost:8000](http://localhost:8000)

## 📥 Clonando o Projeto

Ao clonar este repositório, siga estes passos:

1. Copie o `.env.example` para `.env`:
   ```bash
   cp .env.example .env
   ```

2. Gere a chave da aplicação:
   ```bash
   php artisan key:generate
   ```

3. Instale as dependências:
   ```bash
   composer install
   ```

4. Execute as migrations:
   ```bash
   php artisan migrate
   ```

> ⚠️ **Nota:** O arquivo `.env` não é versionado por conter informações sensíveis. Sempre crie seu próprio arquivo `.env` baseado no `.env.example` ao clonar o projeto.
