#Getting Started

- [Introduction](#introduction)
- [Installation](#installation)
  - [Server Requirements](#server-requirements)
  - [Installing Accio](#installing-accio)
  - [Create Project](#create-project)
  - [Run Accio Installer](#run-accio-installer)
  - [Configuration](#configuration)

## Introduction

Accio is an open source CMS (Content Management System) built with Laravel and Vuejs.

Before you start using Accio for your project, it's highly recommended reading [Laravel](https://laravel.com) and
[Vuejs](https://vuejs.org/) documentation first.

# Installation

## Server requirements
Accio has a few system requirements. By default, the system requirements are satisfied by
[Laravel Homestead](https://laravel.com/docs/5.7/homestead). However, if you are not using Homestead, you will need
to make sure your server meets the following requirements:

- PHP >= 7.1.3
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension
- Ctype PHP Extension
- JSON PHP Extension
- BCMath PHP Extension
- NodeJS and NPM
- Composer
- Redis (Optional)
- Elasticsearch (Optional)

## Installing Accio

### Create Project

First, run the following composer command into your web directory. This will install all dependencies and launch
Accio Installer.

```
composer create-project --prefer-dist acciocms/accio mysite
```

### Run Accio Installer

Go to your project directory, run the following command and follow installerâ€™s questions.

```php
php artisan accio:install
```

If your environment meets Accioâ€™s Server Requirement, your Accio will be ready to go.

### Configuration

Accio needs almost no other configuration out of the box. You are free to get started developing! However,
all of the configuration files for Accio are stored in the config directory and .env file in your project directory.
These files contain several options such as timezone, caching engines, session, database, deploy or project
configuration that you may wish to change according to your application.

# Web Server Configuration

## Apache
Laravel includes a `public/.htaccess` file that is used to provide URLs without the `index.php` front controller in the path. Before serving Laravel with Apache, be sure to enable the  `mod_rewrite` module so the `.htaccess` file will be honored by the server.

If the `.htaccess` file that ships with Accio does not work with your Apache installation, try [Laravel's](https://laravel.com/docs/5.7#pretty-urls) alternative:

## Nginx
If you are using Nginx, the following directive in your site configuration will direct all requests to the index.php front controller:

```php
location / {
    try_files $uri $uri/ /index.php?$query_string;
}
````
