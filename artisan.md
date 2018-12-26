# Artisan

- [Introduction](#introduction)
- [Available commands](#available-commands)
  - [Install Accio](#install-accio)
  - [Check Requirements](#check-requirements)
  - [Make Dummy](#make-dummy)
  - [Dump Database](#dump-database)
  - [Make theme](#make-theme)
  - [Make User](#make-user)
  - [Install Plugin](#install-plugin)
  - [Update Plugin](#update-plugin)
  - [Uninstall Plugin](#uninstall-plugin)
  - [Set write permissions](#set-write-permissions)

# Introduction
Artisan is the command-line interface included with Accio and Laravel.
It provides a number of helpful commands that can assist you while you build your application.
To view a list of all available Artisan commands, you may use the list command:

```php
php artisan list
````

Fore more details regarding how Artisan commands works, please refer to [Laravel Documentation](https://laravel.com/docs/5.7/artisan)

# Available commands
## Install Accio

Initiate a fresh install of Accio.
```php
php artisan accio:install
```
## Check Requirements
Check if your server environment complies to Accio's requirements.
```php
php artisan check:requirements
```
## Make Dummy
This command helps your to bootstrap your database, create good-looking “Lorem Ipsum” content, fill-in your persistence to stress test it, or see how your project performs with a large set of data.

```php
php artisan make:dummy
````
### Options
#### `--all`
Crates dummy content for all default apps.

Default: `false`

```php
php artisan make:dummy --all
````

#### `--users`
Number of users to be created.

Default: `5`
```php
php artisan make:dummy --users=2
````
#### `--role_id`
Role ID that should be assigned to created users.

Default: Editor's role ID
```php
// Create 3 users that belongs to a user role with ID 5
php artisan make:dummy --users=3 --role_id=5
````

#### `--users_per_role`
Number of users to be created for each user role.  `--role_id` and `--users` options are ignored if this option is given.

Default: `0`
```php
// Create 2 users for each of existing user roles
php artisan make:dummy --users_per_role=2
````
#### `--post_types`
Number of post types to be created.

Default: `1`
```php
// Create 2 random post types
php artisan make:dummy --post_types=2
````
#### `--media`
Number of media files (Images) to be created.

Default: `20`
```php
// Create 30 images
php artisan make:dummy --media=30
````

#### `--categories`
Number of categories to be created. If option --post_type is not given, default Post Type is used.

Default: `5`
```php
// Create 2 dummy categories
php artisan make:dummy --categories=2

// Create a dummy category for “Post Pages”
php artisan make:dummy --categories=1 --post_type=post_pages
````

#### `--categories_per_post_type`
Number of categories to create for each of available post types.  Option --categories is ignored if this option is given.

Default: `0`
```php
// Create 3 categories for each of available post type
php artisan make:dummy --categories_per_post_type=3
````

#### `--tags`
Number of tags to be created. If option --post_type is not given, default Post Type is used.
Default: `20`

```php
// Create 5 dummy tags.
php artisan make:dummy --tags=5

// Create 5 dummy tags for the post type “Post Pages”
php artisan make:dummy --tags=5 --post_type=post_pages
````

#### `--tags_per_post_type`
Number of tags to create for each of available post types.  Option --tags is ignored if this option is given.

Default: `
```php
// Create 3 tags for each of available post types.
php artisan make:dummy --tags_per_post_type=3
````

#### `--posts`
Number of posts to be created.
Default: 25
```php
// Create 10 posts in default post type.
php artisan make:dummy --posts=10

// Create 10 posts in “post_pages” table
php artisan make:dummy --posts=10 --post_type=post_pages

// Create 10 posts for each of available post type.
php artisan make:dummy --posts=10 --post_types=all
````

#### `--post_type`
Slug of post type which posts should belong to.
This option is effective only if it is combined with apps that are related to a post type (ex. Categories, tags, posts).

Default: `post_articles`

#### `--posts_per_category`
The number of posts to be created for each category. --posts option is ignored if this option is given.

Default: `0`

```php
// Create 10 posts for each of categories that belongs to “post_article” post type..
php artisan make:dummy --posts_per_category=1 --post_type=post_articles
````

#### `--category`
The “Slug” or “categoryID” of the category which tags/posts should belong to.
Default: `null`

```php
// Create 5 posts that belongs to category 123.
php artisan make:dummy --posts=5 --category=123
````

## Dump Database
Dump your database into an sql file. It works with mysql, pgsql, sqllite, and mongodb.
```php
php artisan db:dumper
````

This command uses [`spatie/dp-dumber`](#https://github.com/spatie/db-dumper) package to perform the dump.

### Options

#### `-path`

The absolute path where you want your database to be dumped.

Default: `{your project directory}/storage/app/dumper/`

You can configure your

### Requirements
For dumping MySQL-db's `mysqldump` should be installed.

For dumping PostgreSQL-db's `pg_dump` should be installed.

For dumping SQLite-db's `sqlite3` should be installed.

For dumping MongoDB-db's `mongodump` should be installed.

> {note} For security reasons, we recommend you to delete your dump after you are done with it.

## Make theme
Creating a basic theme on Accio is an easy job.
The following command generates all necessary files needed to create a simple theme so you start working on your beautiful theme right away.

```php
php artisan make:theme
````
## Make User
If you are in a non-production environment, you may need to create a user without using the Admin Panel.
The following command will create a user based on your input.

Default role: `Editor`

```php
php artisan make:user
````

## Install Plugin
You can easily install Accio Plugins from a public git repository, a zip file or a directory

Example:
```php
// from a git repository
php artisan plugin:install https://github.com/AccioCMS/seo-plugin

// from a zip file
php artisan plugin:install  https://github.com/AccioCMS/seo-plugin/archive/master.zip

// from a directory.
// NOTE: Your should copy your plugin to `plugins` directory and refer to it by its namespace, before executing this command.
php artisan plugin:install  Accio/SEO

````
## Update Plugin
Updating a plugin is just as simply as installing it.

Example:
```php
// Updating from a public git repository.
php artisan plugin:update https://github.com/AccioCMS/seo-plugin

// Updating from a zip file.
php artisan plugin:update https://github.com/AccioCMS/seo-plugin/archive/master.zip
````

## Uninstall Plugin
You can uninstall a plugin by running the following command.

Example:
```php
php artisan plugin:delete Accio/SEO
// where Accio/SEO is the namespace of the plugin
````
## Set write permissions
If you are working on your local environment and need to set full permissions to accio's directories (like storage & boostrap), use the following command.

```php
sudo php artisan set:permissions
````

Running this, will set you full permissions to the following directories:
- storage/tmp
- storage/logs
- storage/framework
- storage/framework/cache
- storage/framework/sessions
- storage/framework/views
- bootstrap/cache

> {note} This command works on local environment only.

## Backup
Accio uses the [`spatie/laravel-backup`](https://github.com/spatie/laravel-backup) package to provide out-of-the-box backup functionality.

On your `config/backup.php` , you can configure which files and databases will be backed up, where and how.

To run a backup of your entire app, execute the following command:
```php
php artisan backup:run
````

The specified databases will be dumped and, together with the selected files, zipped.
The zip file will be named:{specified name in configuration}/{Y-m-d-H-i-s}.zip.

The more files you need to backup, the bigger the zip will become. Make sure there's enough free space on your disk to create the zip file. After the source zip file has been copied to all destinations, it will be deleted.

For more information regarding backup functionality, please follow [package documentation](https://docs.spatie.be/laravel-backup/v5/introduction)