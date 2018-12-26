#Configuration

- [Introduction](#introduction)
- [Environment Configuration](#environment-configuration)
- [Directory Permssions](#directory-permissions)

## Introduction
All of the configuration files for Accio are stored in the `config` directory.
Each option is documented, so feel free to look through the files and get familiar with the options available to you.

## Environment Configuration
It is often helpful to have different configuration values based on the environment where the application is running.
For example, you may wish to use a different cache driver locally than you do on your production server or testing server.

To make this a cinch, Accio utilizes [Laravel's .env configuration files](https://laravel.com/docs/5.7/configuration).
In a fresh Accio installation, the root directory of your application will contain a `.env` file which will get configured during the installation.

Your `.env` file should not be committed to your application's source control, since each developer / server using your application could require a different environment configuration. Furthermore, this would be a security risk in the event an intruder gains access to your source control repository, since any sensitive credentials would get exposed.

If you are developing with a team, you may wish to continue including a .env.production file in which you configure
production configuration and a .env.example file for the development use.
By putting placeholder values in the example configuration file, other developers on your team can clearly see which
environment variables are needed to run your application. You may also create a .env.testing file. This file will
override the .env file when running PHPUnit tests or executing Artisan commands with the --env=testing option.

<a name="directory-permissions"></a>
## Directory Permissions
In order for Accio to work, you need to set write permissions to the following directories, be it on local or production environment.

- storage/tmp
- storage/logs
- storage/framework
- storage/framework/cache
- storage/framework/sessions
- storage/framework/views
- bootstrap/cache
- resources/lang

You can use Accio’s `set:permissions` command to set your permissions in the local environment:

```php
sudo php artisan set:permissions
```

> {note} The above command sets full permissions (0777) to above listed directories. Use it with caution!

For more information regarding environment configuration read [Laravel's official documentation](https://laravel.com/docs/5.7/configuration)