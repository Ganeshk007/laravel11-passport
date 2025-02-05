php artisan install:api --passport


use Laravel\Passport\HasApiTokens;


config/auth.php
'guards' => [
    'web' => [
        'driver' => 'session',
        'provider' => 'users',
    ],
 
    'api' => [
        'driver' => 'passport',
        'provider' => 'users',
    ],
],


php artisan passport:keys


php artisan passport:client --password


App\Providers\AppServiceProvider
public function boot(): void
{
    Passport::enablePasswordGrant();
}

iddleware('auth:api');