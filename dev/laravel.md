# Laravel Projects - Webapp, Website, API

## Laravel Setup Commands

```
composer create-project laravel/laravel <ProjectName>
php artisan make:model <ModelName> --all
```


## Laravel Breeze - Authentication

```
composer require laravel/breeze --dev 
php artisan breeze:install 
npm install
npm run dev
php artisan migrate
```

## Laravel Sanctum - API


```
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
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


## Laravel Telescope - View All Request

```
composer require laravel/telescope
php artisan telescope:install
php artisan vendor:publish --tag=telescope-migrations
php artisan migrate
```

## Laravel Dusk - Automated Testing

```
composer require --dev laravel/dusk
php artisan dusk:install
```

## Laravel Activity Log

```
composer require spatie/laravel-activitylog
php artisan vendor:publish --provider="Spatie\Activitylog\ActivitylogServiceProvider" --tag="activitylog-migrations"
php artisan migrate

```
