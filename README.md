# Directus API Wrapper for Laravel 5

![packagist version](https://img.shields.io/packagist/v/c14r/directus-api-laravel)
![directus version](https://img.shields.io/badge/directus-v8.8.1-blue)
![laravel version](https://img.shields.io/badge/laravel-v8-blue)

This package allows users to easily consume the REST API provided by the Directus Headless CMS system in any Laravel app.

If your looking for an API Wrapper without using Laravel, see [c14r/directus-api](https://github.com/C14r/directus-api).

# Installing

The recommended way to install Directus-API is through
[Composer](https://getcomposer.org/).

```bash
composer require c14r/directus-api-laravel
```

In Laravel 5, update the `config/app.php` providers array with the Service Provider:

```php
C14r\Directus\Laravel\DirectusServiceProvider::class,
```

# Configuration

By default, the package is set up to use the following configuration values from your `.env` file:

+ `DIRECTUS_URL` - The base URL of your Directus instance.
+ `DIRECTUS_PROJECT` - The Directus project, you want to use

## Authentification

You can enter
+ `DIRECTUS_API_KEY` - The key generated by Directus and associated with a user

or

+ `DIRECTUS_USERNAME` - The Directus username
+ `DIRECTUS_PASSWORD` - The password for you Directus user 

If you enter non of them, the guest access is used.

## Laravel

If you would like to use a config file, you can publish the default config by running the following command:

```bash
php artisan vendor:publish --provider="C14r\Directus\Laravel\DirectusServiceProvider"
```

This will publish a config file to `config/directus.php`.

# Usage

To utilize the API Wrapper, use dependency injection to resolve:

```php
public function __construct(Directus $directus)
{
    $this->api = $directus;
}
```

or use the helper function:

```php
directus() // or directus('connection')
```
## How the API works

Take a look at [c14r/directus-api](https://github.com/C14r/directus-api) for more details.
