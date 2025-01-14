<a href="https://codeclimate.com/github/andreacivita/Laravel-ApiCrudGenerator/maintainability"><img src="https://api.codeclimate.com/v1/badges/e22398ed005890048cb5/maintainability" /></a>
[![Latest Stable Version](https://poser.pugx.org/andreacivita/api-crud-generator/v/stable)](https://packagist.org/packages/andreacivita/api-crud-generator)
[![License](https://poser.pugx.org/andreacivita/api-crud-generator/license)](https://packagist.org/packages/andreacivita/api-crud-generator)

# Laravel | API CRUD Generator

This Generator package provides generators of Models, Controllers, Request, Routes & Tests for a painless development. 

## INSTALL

Install the package through [Composer](https://getcomposer.org/).

Run the Composer require command from the Terminal:

```sh
composer require andreacivita/api-crud-generator --dev
```

### SETUP

Run this command from the Terminal

```sh
php artisan vendor:publish
```
Select andreacivita/api-crud-generator and setup it's complete.


## USAGE

### Managing all database
Usage of this package is very simple.

First, let's supposing I want to generate CRUD for all table in my db.

So, we run

```sh
php artisan make:crud --all
```

No further options required. Your setup is complete!


### Interactive mode

You can manage a single table with interactive mode or manually (see [next paragraph](https://github.com/andreacivita/Laravel-ApiCrudGenerator#managing-a-single-db-table)).

Just run

```sh
php artisan make:crud --interactive
```

Crud generator will ask you several data (Name of resource, Table name and use of timestamps).


### Managing a single db table

Now i suppose generation of CRUD operations of Car db table.

Run this command:

```sh
php artisan make:crud Car
```
Done! You will have Car model (located in App/Model directory), CarController, CarRequest (used for input data) and Routes (located in routes/api.php).

### OPTIONS

#### TABLE NAME
By default, DB Table's name is plural, while Model class name is singular (e.g. Table => Cars, Model => Car). 
You can change this behavior specifying the name in terminal

```sh
php artisan make:crud Car --table Car
```
This will create the same resources, but table name in model will be 'Car' (instead of default 'Cars')

#### TIMESTAMPS

By default, this packages will set all timestamps to false. You can change this doing this command:

```sh
php artisan make:crud Car --timestamps true
```

This will set 'timestamps=true' in Model class.

## ROUTING

I developed this package for myself. So, default generation of API Routes will follow this schema:
Example: i'm generating Car crud

| Route         | Method           | Operation        |
| ------------- |:----------------:| ----------------:|
| cars          | GET              | Get all cars     |
| car/{id}      | GET              | Find car by id   |
| car           | PUT              | Insert a new car |
| car/{id}      | PATCH            | Update car by id |
| car/{id}      | DELETE           | Delete car by id |

Remember that all api routes have 'api/' prefix.

## TESTING

When created CRUD structure (Controllers, Models, Request & Routes), this package generate Unit test file. <br>
**IMPORTANT** : Testing insert and update functions are not yet implemented.

## CONTRIBUTING

This package is covered by MIT license. You are able to do whatever you want with this code.

Please feel free to fork this package and contribute by submitting a pull request to enhance the functionalities.
You can see issues or enhancement and assign task for contributing :)


## How can I thank you?

Star this repo or follow me on GitHub. And, if you want, you can share this link! :)



