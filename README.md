## Laravel Permission UI

__Status update: package idea abandoned.__ 

__Unfortunately, it's not possible/easy to build this package as flexible as I was expecting, with different layouts for Tailwind/Bootstrap/whatever and auto-implementing all Spatie package features for all possible cases. So I decided not to pursue this idea further and focus on other projects.__

- - - - -

This package will create a simple Dashboard for managing roles/permissions based on the [spatie/laravel-permission](https://github.com/spatie/laravel-permission) package.

**Notice**: this is a very early version of the package, may be buggy. Please report issues.

- - - - -

## Installation

First, before installing this package, you need to have the `spatie/laravel-permission` installed and configured.

```sh
composer require laraveldaily/laravel-permission-ui
```

Go to `yourdomain.com/permissions` and you should see a simple dashboard with three menu items on top: to manage roles, permissions and assign them to users.

![Spatie Permission UI](https://laraveldaily.com/uploads/2022/10/laravel-permission-ui.png)

That dashboard is by default protected by the `auth` middleware, but you can configure it, by publishing the config:

```sh
php artisan vendor:publish --provider="LaravelDaily\PermissionsUI\PermissionsUIServiceProvider" --tag="config"
```

And then edit the values in `config/permission_ui.php`:

```php
return [
    'middleware'        => ['web', 'auth'],
    'url_prefix'        => 'permissions',
    'route_name_prefix' => 'permission_ui.',
];
```

The visual design is based on simple Tailwind classes. 
At the moment, no visual customization options are available, but we may add them in the future, based on your ideas and feedback.

---

## Testing

To run the package's unit tests, run the following command:

```sh
vendor/bin/phpunit
```
