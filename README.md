# vuexy-laravel-bootstrap-jetstream

[![Latest Stable Version](https://poser.pugx.org/pixinvent/vuexy-laravel-bootstrap-jetstream/v)](//packagist.org/packages/pixinvent/vuexy-laravel-bootstrap-jetstream)
[![License](https://poser.pugx.org/pixinvent/vuexy-laravel-bootstrap-jetstream/license)](//packagist.org/packages/pixinvent/vuexy-laravel-bootstrap-jetstream)

##### Specially customized Laravel jetstream's scaffolding for [Vuexy admin Template](#). It'll not work with any other project.
[Download from packagist](https://packagist.org/packages/pixinvent/vuexy-laravel-bootstrap-jetstream)

## Description

Laravel Jetstream is designed using Tailwind CSS and offers your choice of Livewire or Inertia scaffolding. We have removed the Tailwind CSS dependency and modified the Livewire scaffolding as per our template. __Please note we have not provided Inertia scaffolding yet. This package only works with livewire scaffolding__.

Vuexy Laravel Jetstream is a lightweight laravel package that focuses on the `VIEW` side of [Jetstream](https://github.com/laravel/jetstream) package installed in your Laravel application, so when a swap is performed, the `Action`, `MODEL`, `CONTROLLER`, `Component` and `Action` classes of your project is still 100% handled by Laravel development team with no added layer of complexity.

## Table of Content

- [vuexy-laravel-bootstrap-jetstream](#vuexy-laravel-bootstrap-jetstream)
        - [Specially customized Laravel jetstream's scaffolding for Vuexy admin Template. It'll not work with any other project.](#specially-customized-laravel-jetstreams-scaffolding-for-vuexy-admin-template-itll-not-work-with-any-other-project)
  - [Description](#description)
  - [Table of Content](#table-of-content)
  - [Installation](#installation)
    - [Installing Jetstream](#installing-jetstream)
      - [Install Jetstream With Livewire](#install-jetstream-with-livewire)
    - [Install Vuexy Laravel Bootstrap Jetstream](#install-vuexy-laravel-bootstrap-jetstream)
    - [Finalizing The Installation](#finalizing-the-installation)
    - [Extras](#extras)
      - [Pagination](#pagination)
  - [Credits](#credits)
  - [License](#license)

## Installation

### Installing Jetstream

You may use Composer to install Jetstream into your new Laravel project:

```
composer require laravel/jetstream:3.2.4

```

If you choose to install Jetstream through Composer, you should run the jetstream:install Artisan command. This command accepts the name of the stack you prefer (livewire). You are highly encouraged to read through the entire documentation of Livewire before beginning your Jetstream project. In addition, you may use the __--teams__ switch to enable team support:

#### Install Jetstream With Livewire

```bash
// without teams support

php artisan jetstream:install livewire

or

// with teams support

php artisan jetstream:install livewire --teams
```

### Install Vuexy Laravel Bootstrap Jetstream

Use Composer to install Vuexy Jetstream into your new Laravel project as dev dependency:

```
composer require pixinvent/vuexy-laravel-bootstrap-jetstream
```

Regardless how you install Jetstream, Vuexy Laravel Bootstrap Jetstream commands are very similar to that

of Jetstream as it accepts the name of the stack you would like to swap (livewire).

> It is important you install and configure [Laravel Jetstream](https://github.com/laravel/jetstream) before performing a swap.

You are highly encouraged to read through the entire documentation of [Jetstream](https://jetstream.laravel.com/1.x/introduction.html)

before beginning your Vuexy Laravel Jetstream project. In addition, you may use the `--teams` switch to swap team assets just like you would in Jetstream:

```bash
// without teams support

php artisan jetstream_vuexy:swap livewire


or

// with teams support

php artisan jetstream_vuexy:swap livewire --teams

```

This will publish overrides to enable Bootstrap like the good old days!

### Finalizing The Installation

After installing Vuexy Jetstream and swapping Jetstream resources, remove tailwindCSS and its dependencies if any from your package.json and then install and build your NPM dependencies and migrate your database:

```
npm install && npm run dev

or  

yarn && yarn dev


php artisan migrate
```

### Extras

#### Pagination

It is also important to point out that Laravel still includes pagination views built using Bootstrap CSS. To use these views instead of the default Tailwind views, you may call the paginator's useBootstrap method within your AppServiceProvider:

```php
<?php

namespace  App\Providers;

use Illuminate\Support\ServiceProvider;
use Illuminate\Pagination\Paginator;

class  AppServiceProvider  extends  ServiceProvider{

/**
* Register any application services.
*
* @return  void
*/

public  function  register(){

//
  
}

/**
* Bootstrap any application services.
* @return  void
*/

public  function  boot(){

Paginator::useBootstrap();

}

}
```

## Credits

This packages is built on top of [Jetstream](https://github.com/laravel/jetstream) & [Jetstrap](https://github.com/nascent-africa/jetstrap)

## License

Vuexy Jetstream is open-sourced software licensed under the [MIT license](https://github.com/pixinvent/vuexy-laravel-bootstrap-jetstream/blob/vuexy/LICENSE).
