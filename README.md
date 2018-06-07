# Laravel Migrations Generator

[![Build Status](https://travis-ci.org/Xethron/migrations-generator.svg)](https://travis-ci.org/Xethron/migrations-generator)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/Xethron/migrations-generator/badges/quality-score.png?s=41d919c6d044749cb8575bb936efbddc4cebc0d8)](https://scrutinizer-ci.com/g/Xethron/migrations-generator/)
[![Latest Stable Version](https://poser.pugx.org/listenwei/migrations-generator/v/stable.png)](https://packagist.org/packages/listenwei/migrations-generator)
[![Total Downloads](https://poser.pugx.org/listenwei/migrations-generator/downloads.png)](https://packagist.org/packages/listenwei/migrations-generator)
[![License](https://poser.pugx.org/listenwei/migrations-generator/license.png)](https://packagist.org/packages/listenwei/migrations-generator)

Generate Laravel4 Migrations from an existing database, including indexes and foreign keys!

## Laravel 4 installation

```bash
composer require listenwei/l4-migrations-generator
```

Next, add the following service providers:

```
'Way\Generators\GeneratorsServiceProvider',
'Xethron\MigrationsGenerator\MigrationsGeneratorServiceProvider',
```

And you're set. To double check if its working, run `php artisan`, and look for the command `migrate:generate`

## Usage

To generate migrations from a database, you need to have your database setup in Laravel's Config.

Run `php artisan migrate:generate` to create migrations for all the tables, or you can specify the tables you wish to generate using `php artisan migrate:generate table1,table2,table3,table4,table5`. You can also ignore tables with `--ignore="table3,table4,table5"`

Laravel Migrations Generator will first generate all the tables, columns and indexes, and afterwards setup all the foreign key constraints. So make sure you include all the tables listed in the foreign keys so that they are present when the foreign keys are created.

You can also specify the connection name if you are not using your default connection with `--connection="connection_name"`

Run `php artisan help migrate:generate` for a list of options.

