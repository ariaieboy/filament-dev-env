## Clone the project

```git clone git@github.com:ariaieboy/filament-dev-env.git```

go to laravel directory:

```cd filament-dev-env/laravel```

copy the env file:

``` cp .env.example .env ```

## using the project

You can use this project by local PHP installed on your machine or using Laravel Sail and docker.

The steps below tell you how you can use this project using Laravel Sail and docker you can use the same steps and run the project using your Local PHP installation.

## install dependencies

since this repo use [laravel sail](https://laravel.com/docs/9.x/sail) and docker we provide docker commands for
installing and running the project.

for installing composer u can use shortcut command below if u have zsh
and [laravel-sail](https://github.com/ariaieboy/laravel-sail):
`s cinit`
or you can run the actual command :

```bash
    docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v $(pwd):/var/www/html \
    -v $(pwd)/../packages/.:/var/www/packages \
    -w /var/www/html \
    laravelsail/php82-composer:latest \
    composer install --ignore-platform-reqs
```

## running the project

now if u have zsh and the laravel-sail plugin you can use this command :
`sup`
or you can use command below if you want run it without shortcut:
`./vendor/bin/sail up`

## run migration

By default, we use Sqlite database you can change this by editing the `.env` file and using any database you want.

for first attempt u need to migrate the db using this commands :
`sa migrate` if you have laravel-sail or
`./vendor/bin/sail artisan migrate`

## create user to access filament

for first attempt u need to create user to access to filament using this command:
`sa make:filament-user` if you have laravel-sail plugin or
`./vendor/bin/sail artisan make:filament-user`

## create packages

you can create your package and clone it in the packages directory then you can install it using this commands :

``` sc require yourname/your-package-name```
if you don't have laravel-sail plugin you can use this command:
```./vendor/bin/sail composer require yourname/your-package-name```