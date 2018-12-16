#Directory Structure

- [Introduction](#introduction)
- [The Content Management System](#the-content-management-system)
- [Core Package](#core-package)


<a name="introduction"></a>
## Introduction

<a name="cms"></a>
## The Content Management System
Before **reading** further, we suggest you read [Laravel official structure](#https://laravel.com/docs/master/structure) documentation.

Ne baze struktura e accio eshte e njejt si e laravelit, sidoqofte, Accio vjen me disa pre-set Middlewares, Controllers, Models, Listeners, qe ju ndihmon me customize projektin tuaj shpejt, a najsen.

Kjo eshte lista e ndryshimeve prej paketes zyrtare:

- app
    - Http
        - Controllers
            - [Frontend](#cms-frontend-directory)
            - [Backend](#cms-backend-directory)
        - [Middleware](#middleware-directory)
    - [Listeners](#cms-listeners-directory)
    - [Models](#cms-models-directory)
    - [Notifications](#cms-notifications-directory)
- [plugins](#plugins-directory)
- [routes](#cms-routes-directory)

<a name="frontend-controllers"></a>
### CMS `Frontend` Directory

<a name="backend-controllers"></a>

### CMS `Backend` Directory

<a name="middleware"></a>
### CMS `Middleware` Directory

<a name="listeners"></a>
### CMS `Listeners` Directory

<a name="models"></a>
### CMS `Models` Directory

<a name="notifications"></a>
### CMS `Notifications` Directory

<a name="plugins"></a>
###  `Plugins` Directory
cila eshte struktura e pluginave dhe qysh krijohet kah nje follder per çdo plugin qe instalohet ne kuader te autorit

<a name="routes"></a>
### CMS `Routes` Directory
qysh i kena nda routat ne fajlla

<a name="core"></a>
## Core Package
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

### `Commands` Directory

### `Deploy` Directory

### `Api` Directory

### `Backend` Directory

### `Frontend` Directory

### `Middleware` Directory

### `Providers` Directory

### `Interfaces` Directory

### `Models` Directory

### `Services` Directory

### `Traits` Directory

### `Resources` Directory
me fol per

#### assets

#### lang

#### scripts

#### views

### `support` Directory
### `Facades` Directory
### `stubs` Directory
