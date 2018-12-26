# Directory Structure

- [Introduction](#introduction)
- [The Content Management System](#the-content-management-system)
- [The Core Package](#the-core-package)

<a name="introduction"></a>
## Introduction
The default structure of Accio is intended to provide a great starting point for both small and large applications.

Before **reading** further, we suggest you read [Laravel official structure](#https://laravel.com/docs/master/structure) documentation.

<a name="cms"></a>
## The Content Management System
At its core, Accio's structure is the same as Laravel, however, it comes with some pre-set Middleware, Controllers, Models & Listeners that can help you kick-off your next project right away.

The following directories highlighted in bold shows Accio's pre-set directories.

- app
    - Http
        - Controllers
            - [**Frontend**](#the-frontend-cms-directory)
            - [**Backend**](#the-backend-cms-directory)
        - [**Middleware**](#the-middleware-cms-directory)
    - [**Listeners**](#the-listeners-cms-directory)
    - [**Models**](#the-models-cms-directory)
    - [**Notifications**](#the-notifications-cms-directory)
- [**plugins**](#the-plugins-cms-directory)
- [**routes**](#the-routes-cms-directory)

### The Frontend CMS Directory
The `Frontend` directory contains a `MainController.php` which is extended by all Theme controllers.

Other frontend controllers are theme-based, and can be found within your active theme directory.

### The Backend CMS Directory
The `Backend` directory contains all backend controllers. They don't include any preset functionality, however, they extend accio's respective backend controllers that provide the core functionality of Accio's Admin panel.
If you need customize functionality, you may overwrite Accio's methods on each respective controller.

### The Middleware CMS Directory
The `Middleware` directory contains default Laravel Middlewares as well as custom Accio Middlewares, which you are free to overwrite, if you need custom functionality.

### The Listeners CMS Directory
The `Listeners` directory contains the classes that handle your events. Event listeners receive an event instance and perform logic in response to the event being fired.

### The Models CMS Directory
Unlike Laravel, we choosed to place models within `Models` directory. Accio comes with a list of pre-set models, which extend functionality from Accio's core package.
If you need custom functionality of pre-set models, you can overwrite respective methods and properties.

### The Notifications CMS Directory
The `Notifications` directory contains all of the "transactional" notifications that are sent by your application, such as simple notifications about events that happen within your application.

### The Plugins CMS Directory
The `plugins` directory contains all of the Plugins installed on Accio. Every plugin installed will be stored within author's name. Example:

- plugins
  - Accio
    - SEO

### The Routes CMS Directory
The `routes` directory contains all of the route definitions for your application. By default, several route files are included with Accio:

- account.php //@todo me  fshi account by default, nese don me pas auth functionalities, le te jet nje komand qe e shton kete funksionalitet
- auth.php (@todo njejt me e ba me komande)
- base.php
- category.php
- post_articles.php
- post_pages.php
- search.php
- tag.php
- user.php
- web.php
- api.php
- console.php
- channels.php

As you may notice, routes are saved in individual apps, based on their purpose.

## The Core Package
Krejt funkcionaliteti i cms-it eshte qetu. funksionon si paket e pa varur, blla blla.

- app
    - [Commands](#commands-directory)
        - Deploy
    - Http
        - Controllers
            - [Api](#api-directory)
                - {version}
            - [Backend](#backend-directory)
            - [Frontend](#frontend-directory)
        - [Middleware](#middleware-directory)
        - [Providers](#providers-directory)
    - [Interfaces](#interfaces-directory)
    - [Models](#models-directory)
    - [Services](#services-directory)
    - [Traits](#traits-directory)
- [Resources](#resources-directory)
- [support](#support-directory)
    - [Facades](#facades-directory)
    - [stubs](#stubs-directory)

### Commands Directory

### Deploy Directory

### Api Directory

### Backend Directory

### Frontend Directory

### Middleware Directory

### Providers Directory

### Interfaces Directory

### Models Directory

### Services Directory

### Traits Directory

### Resources Directory
me fol per

#### assets

#### lang

#### scripts

#### views

### support Directory
### Facades Directory
### stubs Directory
