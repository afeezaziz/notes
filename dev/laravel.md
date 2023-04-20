# Laravel Projects - Webapp, Website, API

## Laravel Setup Commands

```
composer create-project laravel/laravel <ProjectName>
php artisan make:model <ModelName> --all
```

## Laravel Fortify - Authentication

```
composer require laravel/fortify
php artisan vendor:publish --provider="Laravel\Fortify\FortifyServiceProvider"
```

in app\Providers\FortifyServiceProvider.php
```
        Fortify::loginView(function () {
            return view('authentication.login');
        });

        Fortify::registerView(function (Request $request) {
            if ($request->has('user_type')) {
                if ($request->get('user_type') == 'brand') {
                    $user_type = 'brand';    
                } else {
                    $user_type = 'creator';    
                }
            } else {
                $user_type = 'none';
            }
            return view('authentication.register', compact('user_type'));
        });

        Fortify::requestPasswordResetLinkView(function () {
            return view('authentication.forgot-password');
        });
        
        Fortify::resetPasswordView(function ($request) {
            return view('authentication.reset-password', ['request' => $request]);
        });   
        
        Fortify::confirmPasswordView(function () {
            return view('authentication.confirm-password');
        });
```

in config/app.php

```
        App\Providers\FortifyServiceProvider::class,
```

## Tailwind Setup

```
npm install -D tailwindcss postcss autoprefixer @tailwindcss/forms
npx tailwindcss init -p
```

in resources/css/app.css
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

in resources/js/app.js
```
import './bootstrap';
import '../css/app.css'
```

in tailwind.config.js
```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./resources/**/*.blade.php",
    "./resources/**/*.js",
    "./resources/**/*.vue",    
  ],
  theme: {
    extend: {},
  },
  plugins: [
    require('@tailwindcss/forms'),
  ],
}


```

## Laravel Sanctum - API


```
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
php artisan migrate
```


## Laravel Activity Log

```
composer require spatie/laravel-activitylog
php artisan vendor:publish --provider="Spatie\Activitylog\ActivitylogServiceProvider" --tag="activitylog-migrations"
php artisan migrate

```

## Others

### Laravel Telescope - View All Request

```
composer require laravel/telescope
php artisan telescope:install
php artisan vendor:publish --tag=telescope-migrations
php artisan migrate
```

### Laravel Dusk - Automated Testing

```
composer require --dev laravel/dusk
php artisan dusk:install
```

### Laravel Breeze - Authentication

```
composer require laravel/breeze --dev 
php artisan breeze:install 
npm install
npm run dev
php artisan migrate
```


## Laravel Laratrust - RBAC

```
composer require santigarcor/laratrust
php artisan vendor:publish --tag="laratrust"
php artisan laratrust:setup
php artisan vendor:publish --tag=laratrust-assets --force
composer dump-autoload
php artisan migrate
```

## Laravel Scout - Full Text Search

```
composer require laravel/scout
php artisan vendor:publish --provider="Laravel\Scout\ScoutServiceProvider"
```
