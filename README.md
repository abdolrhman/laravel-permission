# Associate users with permissions and roles

[![Latest Version on Packagist](https://img.shields.io/packagist/v/spatie/laravel-permission.svg?style=flat-square)](https://packagist.org/packages/spatie/laravel-permission)
[![Build Status](https://img.shields.io/travis/spatie/laravel-permission/master.svg?style=flat-square)](https://travis-ci.org/spatie/laravel-permission)
[![StyleCI](https://styleci.io/repos/42480275/shield)](https://styleci.io/repos/42480275)
[![Total Downloads](https://img.shields.io/packagist/dt/spatie/laravel-permission.svg?style=flat-square)](https://packagist.org/packages/spatie/laravel-permission)

Thanks to <img style="width:90px; height:30px; vertical-align:middle;" 
    src="data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiIHN0YW5kYWxvbmU9Im5vIj8+Cjxzdmcgd2lkdGg9IjQ2MnB4IiBoZWlnaHQ9IjE2OHB4IiB2aWV3Qm94PSIwIDAgNDYyIDE2OCIgdmVyc2lvbj0iMS4xIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB4bWxuczpza2V0Y2g9Imh0dHA6Ly93d3cuYm9oZW1pYW5jb2RpbmcuY29tL3NrZXRjaC9ucyI+CiAgICA8IS0tIEdlbmVyYXRvcjogU2tldGNoIDMuMC4zICg3ODkxKSAtIGh0dHA6Ly93d3cuYm9oZW1pYW5jb2RpbmcuY29tL3NrZXRjaCAtLT4KICAgIDx0aXRsZT5VbnRpdGxlZDwvdGl0bGU+CiAgICA8ZGVzYz5DcmVhdGVkIHdpdGggU2tldGNoLjwvZGVzYz4KICAgIDxkZWZzPjwvZGVmcz4KICAgIDxnIGlkPSJQYWdlLTEiIHN0cm9rZT0ibm9uZSIgc3Ryb2tlLXdpZHRoPSIxIiBmaWxsPSJub25lIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIHNrZXRjaDp0eXBlPSJNU1BhZ2UiPgogICAgICAgIDxnIGlkPSJsb2dvLWJsdWUtaG9yaXpvbnRhbCIgc2tldGNoOnR5cGU9Ik1TTGF5ZXJHcm91cCI+CiAgICAgICAgICAgIDxnIGlkPSJHcm91cCIgc2tldGNoOnR5cGU9Ik1TU2hhcGVHcm91cCI+CiAgICAgICAgICAgICAgICA8ZyBpZD0iQ2xpcHBlZCIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTg4LjAwMDAwMCwgNDQuMDAwMDAwKSIgZmlsbD0iIzE2MjE0RCI+CiAgICAgICAgICAgICAgICAgICAgPHBhdGggZD0iTTI0Ni41MTcsMC4xMSBDMjM4LjQzOSwwLjExIDIzMS42MDcsMy45MTYgMjI2Ljc1OSwxMS4xMTUgQzIyMS45NCwxOC4yNzEgMjE5LjM5MywyOC4yNiAyMTkuMzkzLDQwIEMyMTkuMzkzLDUxLjc0IDIyMS45NCw2MS43MjkgMjI2Ljc1OSw2OC44ODQgQzIzMS42MDcsNzYuMDg0IDIzOC40MzksNzkuODg5IDI0Ni41MTcsNzkuODg5IEMyNTQuNTk1LDc5Ljg4OSAyNjEuNDI3LDc2LjA4NCAyNjYuMjc1LDY4Ljg4NCBDMjcxLjA5Myw2MS43MjkgMjczLjY0LDUxLjc0IDI3My42NCw0MCBDMjczLjY0LDI4LjI2IDI3MS4wOTMsMTguMjcxIDI2Ni4yNzUsMTEuMTE1IEMyNjEuNDI3LDMuOTE2IDI1NC41OTUsMC4xMSAyNDYuNTE3LDAuMTEgTDI0Ni41MTcsMC4xMSBaIE0yNDYuNTE3LDcwLjAwNSBDMjQyLjY1NSw3MC4wMDUgMjM5LjYwNCw2Ny44MiAyMzcuMTg3LDYzLjMyNCBDMjM0LjI2OCw1Ny44OTMgMjMyLjY2LDQ5LjYxIDIzMi42Niw0MCBDMjMyLjY2LDMwLjM5IDIzNC4yNjgsMjIuMTA2IDIzNy4xODcsMTYuNjc2IEMyMzkuNjA0LDEyLjE4IDI0Mi42NTUsOS45OTQgMjQ2LjUxNyw5Ljk5NCBDMjUwLjM3OCw5Ljk5NCAyNTMuNDMsMTIuMTggMjU1Ljg0NywxNi42NzYgQzI1OC43NjYsMjIuMTA2IDI2MC4zNzMsMzAuMzg5IDI2MC4zNzMsNDAgQzI2MC4zNzMsNDkuNjExIDI1OC43NjYsNTcuODk1IDI1NS44NDcsNjMuMzI0IEMyNTMuNDMsNjcuODIgMjUwLjM3OCw3MC4wMDUgMjQ2LjUxNyw3MC4wMDUgTDI0Ni41MTcsNzAuMDA1IFogTTcxLjQ1LDI5LjE3MiBMNzEuNDUsNjMuNDg0IEM3MS40NSw3Mi41MyA3OC44MSw3OS44ODkgODcuODU2LDc5Ljg4OSBDOTUuNzQ2LDc5Ljg4OSAxMDEuNzA3LDc1Ljk3NSAxMDMuOTAyLDc0LjI5MSBDMTA0LjAyNCw3NC4xOTcgMTA0LjE4NCw3NC4xNjkgMTA0LjMzMSw3NC4yMTYgQzEwNC40NzgsNzQuMjYzIDEwNC41OTIsNzQuMzc5IDEwNC42MzcsNzQuNTI3IEwxMDUuOTYxLDc4Ljg2IEwxMTUuNzM3LDc4Ljg2IEwxMTUuNzM3LDI5LjE3MiBMMTAzLjE3NSwyOS4xNzIgTDEwMy4xNzUsNjYuMzI2IEMxMDMuMTc1LDY2LjUwMSAxMDMuMDc2LDY2LjY2MiAxMDIuOTIxLDY2Ljc0MyBDMTAwLjU1OSw2Ny45NjEgOTUuODk5LDcwLjAwNiA5MS4yMzEsNzAuMDA2IEM4Ny4yNTIsNzAuMDA2IDg0LjAxMiw2Ni43NjggODQuMDEyLDYyLjc4NyBMODQuMDEyLDI5LjE3MiBMNzEuNDUsMjkuMTcyIEw3MS40NSwyOS4xNzIgWiBNMTk3LjIzNyw3OC44NTkgTDIwOS44LDc4Ljg1OSBMMjA5LjgsNDQuNTQ3IEMyMDkuOCwzNS41MDEgMjAyLjQ0LDI4LjE0MSAxOTMuMzk0LDI4LjE0MSBDMTg2LjczNSwyOC4xNDEgMTgxLjM5MywzMS4wMDQgMTc4LjgwMiwzMi43MSBDMTc4LjY1NywzMi44MDUgMTc4LjQ3MywzMi44MTMgMTc4LjMyMiwzMi43MzEgQzE3OC4xNzEsMzIuNjQ5IDE3OC4wNzUsMzIuNDkxIDE3OC4wNzUsMzIuMzE4IEwxNzguMDc1LDEuMTQxIEwxNjUuNTEzLDEuMTQxIEwxNjUuNTEzLDc4Ljg1OSBMMTc4LjA3NSw3OC44NTkgTDE3OC4wNzUsNDEuNzA0IEMxNzguMDc1LDQxLjUyOSAxNzguMTc0LDQxLjM2OCAxNzguMzMsNDEuMjg4IEMxODAuNjkxLDQwLjA2OSAxODUuMzUyLDM4LjAyNSAxOTAuMDE5LDM4LjAyNSBDMTkxLjk0NywzOC4wMjUgMTkzLjc2LDM4Ljc3NiAxOTUuMTIzLDQwLjEzOSBDMTk2LjQ4Niw0MS41MDIgMTk3LjIzNiw0My4zMTYgMTk3LjIzNiw0NS4yNDMgTDE5Ny4yMzYsNzguODU5IEwxOTcuMjM3LDc4Ljg1OSBaIE0xMjQuNzkyLDM5LjA1NSBMMTMyLjQzOCwzOS4wNTUgQzEzMi42OTcsMzkuMDU1IDEzMi45MDcsMzkuMjY1IDEzMi45MDcsMzkuNTI0IEwxMzIuOTA3LDY2Ljg1OCBDMTMyLjkwNyw3NC4wNDMgMTM4Ljc1Myw3OS44ODggMTQ1LjkzOCw3OS44ODggQzE0OC41NDMsNzkuODg4IDE1MS4xMTMsNzkuNTEyIDE1My41ODUsNzguNzcgTDE1My41ODUsNjkuNzk2IEMxNTIuMTQzLDY5LjkyMyAxNTAuNDg1LDcwLjAwNSAxNDkuMzEzLDcwLjAwNSBDMTQ3LjE5Myw3MC4wMDUgMTQ1LjQ2OSw2OC4yOCAxNDUuNDY5LDY2LjE2MSBMMTQ1LjQ2OSwzOS41MjMgQzE0NS40NjksMzkuMjY0IDE0NS42NzksMzkuMDU0IDE0NS45MzgsMzkuMDU0IEwxNTMuNTg1LDM5LjA1NCBMMTUzLjU4NSwyOS4xNzEgTDE0NS45MzgsMjkuMTcxIEMxNDUuNjc5LDI5LjE3MSAxNDUuNDY5LDI4Ljk2MSAxNDUuNDY5LDI4LjcwMiBMMTQ1LjQ2OSwxMi4yOTUgTDEzMi45MDcsMTIuMjk1IEwxMzIuOTA3LDI4LjcwMiBDMTMyLjkwNywyOC45NjEgMTMyLjY5NywyOS4xNzEgMTMyLjQzOCwyOS4xNzEgTDEyNC43OTIsMjkuMTcxIEwxMjQuNzkyLDM5LjA1NSBMMTI0Ljc5MiwzOS4wNTUgWiBNNTEuMzYxLDc4Ljg1OSBMNjQuNDI5LDc4Ljg1OSBMNDQuNTU1LDkuNTUgQzQyLjk2MiwzLjk5MiAzNy44MTEsMC4xMSAzMi4wMjksMC4xMSBDMjYuMjQ3LDAuMTEgMjEuMDk2LDMuOTkyIDE5LjUwMiw5LjU1IEwtMC4zNzIsNzguODU5IEwxMi42OTcsNzguODU5IEwxOC40NDksNTguNzk4IEMxOC41MDcsNTguNTk3IDE4LjY5MSw1OC40NTkgMTguOSw1OC40NTkgTDQ1LjE1OCw1OC40NTkgQzQ1LjM2Nyw1OC40NTkgNDUuNTUyLDU4LjU5NyA0NS42MDksNTguNzk4IEw1MS4zNjEsNzguODU5IEw1MS4zNjEsNzguODU5IFogTTQyLjA1Niw0OC41NzYgTDIyLjAwNCw0OC41NzYgQzIxLjg1Nyw0OC41NzYgMjEuNzE4LDQ4LjUwNyAyMS42MjksNDguMzg4IEMyMS41NDEsNDguMjcyIDIxLjUxMyw0OC4xMTkgMjEuNTUzLDQ3Ljk3OCBMMzEuNTc5LDEzLjAxMiBDMzEuNjM3LDEyLjgxMSAzMS44MjEsMTIuNjczIDMyLjAzLDEyLjY3MyBDMzIuMjM5LDEyLjY3MyAzMi40MjMsMTIuODExIDMyLjQ4LDEzLjAxMiBMNDIuNTA3LDQ3Ljk3OCBDNDIuNTQ3LDQ4LjEyIDQyLjUxOSw0OC4yNzIgNDIuNDMsNDguMzg4IEM0Mi4zNDIsNDguNTA3IDQyLjIwMyw0OC41NzYgNDIuMDU2LDQ4LjU3NiBMNDIuMDU2LDQ4LjU3NiBaIiBpZD0iU2hhcGUiPjwvcGF0aD4KICAgICAgICAgICAgICAgIDwvZz4KICAgICAgICAgICAgICAgIDxnIGlkPSJDbGlwcGVkIiBmaWxsPSIjRUI1NDI0Ij4KICAgICAgICAgICAgICAgICAgICA8cGF0aCBkPSJNMTE5LjU1NSwxMzUuODYxIEwxMDIuNzA1LDgzLjk5NyBMMTQ2LjgxMyw1MS45NTIgTDkyLjI5MSw1MS45NTIgTDc1LjQ0LDAuMDkgTDc1LjQzNSwwLjA3NiBMMTI5Ljk2NSwwLjA3NiBMMTQ2LjgyLDUxLjk0NyBMMTQ2LjgyMSw1MS45NDYgTDE0Ni44MzUsNTEuOTM4IEMxNTYuNjIzLDgyLjAzIDE0Ni41NDIsMTE2LjI1NiAxMTkuNTU1LDEzNS44NjEgTDExOS41NTUsMTM1Ljg2MSBaIE0zMS4zMjEsMTM1Ljg2MSBMMzEuMzA3LDEzNS44NzEgTDc1LjQyNiwxNjcuOTI0IEwxMTkuNTU1LDEzNS44NjIgTDc1LjQ0LDEwMy44MDggTDMxLjMyMSwxMzUuODYxIEwzMS4zMjEsMTM1Ljg2MSBaIE00LjA1Miw1MS45MzkgTDQuMDUyLDUxLjkzOSBDLTYuMjUyLDgzLjY2IDUuNzA5LDExNy4yNzIgMzEuMzEyLDEzNS44NjcgTDMxLjMxNiwxMzUuODUxIEw0OC4xNjgsODMuOTkgTDQuMDcsNTEuOTUxIEw1OC41NzksNTEuOTUxIEw3NS40MzEsMC4wODkgTDc1LjQzNSwwLjA3NSBMMjAuOTAyLDAuMDc1IEw0LjA1Miw1MS45MzkgTDQuMDUyLDUxLjkzOSBaIiBpZD0iU2hhcGUiPjwvcGF0aD4KICAgICAgICAgICAgICAgIDwvZz4KICAgICAgICAgICAgPC9nPgogICAgICAgIDwvZz4KICAgIDwvZz4KPC9zdmc+"> for supporting this package. <a href="#sponsor">Read more…</a>

* [Installation](#installation)
* [Usage](#usage)
  * [Using "direct" permissions](#using-direct-permissions-see-below-to-use-both-roles-and-permissions)
  * [Using permissions via roles](#using-permissions-via-roles)
  * [Using Blade directives](#using-blade-directives)
  * [Using multiple guards](#using-multiple-guards)
  * [Using a middleware](#using-a-middleware)
  * [Using artisan commands](#using-artisan-commands)
* [Unit Testing](#unit-testing)
* [Database Seeding](#database-seeding)
* [Extending](#extending)
* [Cache](#cache)

This package allows you to manage user permissions and roles in a database.

Once installed you can do stuff like this:

```php
// Adding permissions to a user
$user->givePermissionTo('edit articles');

// Adding permissions via a role
$user->assignRole('writer');

$role->givePermissionTo('edit articles');
```

If you're using multiple guards we've got you covered as well. Every guard will have its own set of permissions and roles that can be assigned to the guard's users. Read about it in the [using multiple guards](#using-multiple-guards) section of the readme.

Because all permissions will be registered on [Laravel's gate](https://laravel.com/docs/5.5/authorization), you can test if a user has a permission with Laravel's default `can` function:

```php
$user->can('edit articles');
```

Spatie is a web design agency in Antwerp, Belgium. You'll find an overview of all
our open source projects [on our website](https://spatie.be/opensource).

## Installation

- [Laravel](#laravel)
- [Lumen](#lumen)

### Laravel

This package can be used in Laravel 5.4 or higher. If you are using an older version of Laravel, take a look at [the v1 branch of this package](https://github.com/spatie/laravel-permission/tree/v1).

You can install the package via composer:

``` bash
composer require spatie/laravel-permission
```

In Laravel 5.5 the service provider will automatically get registered. In older versions of the framework just add the service provider in `config/app.php` file:

```php
'providers' => [
    // ...
    Spatie\Permission\PermissionServiceProvider::class,
];
```

You can publish [the migration](https://github.com/spatie/laravel-permission/blob/master/database/migrations/create_permission_tables.php.stub) with:

```bash
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider" --tag="migrations"
```

After the migration has been published you can create the role- and permission-tables by running the migrations:

```bash
php artisan migrate
```

You can publish the config file with:

```bash
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider" --tag="config"
```

When published, [the `config/permission.php` config file](https://github.com/spatie/laravel-permission/blob/master/config/permission.php) contains:

```php
return [

    'models' => [

        /*
         * When using the "HasRoles" trait from this package, we need to know which
         * Eloquent model should be used to retrieve your permissions. Of course, it
         * is often just the "Permission" model but you may use whatever you like.
         *
         * The model you want to use as a Permission model needs to implement the
         * `Spatie\Permission\Contracts\Permission` contract.
         */

        'permission' => Spatie\Permission\Models\Permission::class,

        /*
         * When using the "HasRoles" trait from this package, we need to know which
         * Eloquent model should be used to retrieve your roles. Of course, it
         * is often just the "Role" model but you may use whatever you like.
         *
         * The model you want to use as a Role model needs to implement the
         * `Spatie\Permission\Contracts\Role` contract.
         */

        'role' => Spatie\Permission\Models\Role::class,

    ],

    'table_names' => [

        /*
         * When using the "HasRoles" trait from this package, we need to know which
         * table should be used to retrieve your roles. We have chosen a basic
         * default value but you may easily change it to any table you like.
         */

        'roles' => 'roles',

        /*
         * When using the "HasRoles" trait from this package, we need to know which
         * table should be used to retrieve your permissions. We have chosen a basic
         * default value but you may easily change it to any table you like.
         */

        'permissions' => 'permissions',

        /*
         * When using the "HasRoles" trait from this package, we need to know which
         * table should be used to retrieve your models permissions. We have chosen a
         * basic default value but you may easily change it to any table you like.
         */

        'model_has_permissions' => 'model_has_permissions',

        /*
         * When using the "HasRoles" trait from this package, we need to know which
         * table should be used to retrieve your models roles. We have chosen a
         * basic default value but you may easily change it to any table you like.
         */

        'model_has_roles' => 'model_has_roles',

        /*
         * When using the "HasRoles" trait from this package, we need to know which
         * table should be used to retrieve your roles permissions. We have chosen a
         * basic default value but you may easily change it to any table you like.
         */

        'role_has_permissions' => 'role_has_permissions',
    ],

    /*
     * By default all permissions will be cached for 24 hours unless a permission or
     * role is updated. Then the cache will be flushed immediately.
     */

    'cache_expiration_time' => 60 * 24,
];
```

### Lumen

You can install the package via Composer:

``` bash
composer require spatie/laravel-permission
```

Copy the required files:

```bash
cp vendor/spatie/laravel-permission/config/permission.php config/permission.php
cp vendor/spatie/laravel-permission/database/migrations/create_permission_tables.php.stub database/migrations/2018_01_01_000000_create_permission_tables.php
```

You will also need to create another configuration file at `config/auth.php`. Get it on the Laravel repository or just run the following command:

```bash
curl -Ls https://raw.githubusercontent.com/laravel/lumen-framework/5.5/config/auth.php -o config/auth.php
```

Now, run your migrations:

```bash
php artisan migrate
```

Then, in `bootstrap/app.php`, register the middlewares:

```php
$app->routeMiddleware([
    'auth'       => App\Http\Middleware\Authenticate::class,
    'permission' => Spatie\Permission\Middlewares\PermissionMiddleware::class,
    'role'       => Spatie\Permission\Middlewares\RoleMiddleware::class,
]);
```

As well as the configuration and the service provider:

```php
$app->configure('permission');
$app->register(Spatie\Permission\PermissionServiceProvider::class);
```

## Usage

First, add the `Spatie\Permission\Traits\HasRoles` trait to your `User` model(s):

```php
use Illuminate\Foundation\Auth\User as Authenticatable;
use Spatie\Permission\Traits\HasRoles;

class User extends Authenticatable
{
    use HasRoles;

    // ...
}
```

> - note that if you need to use `HasRoles` trait with another model ex.`Page` you will also need to add `protected $guard_name = 'web';` as well to that model or you would get an error
>
>```php
>use Illuminate\Database\Eloquent\Model;
>use Spatie\Permission\Traits\HasRoles;
>
>class Page extends Model
>{
>    use HasRoles;
>
>    protected $guard_name = 'web'; // or whatever guard you want to use
>
>    // ...
>}
>```

This package allows for users to be associated with permissions and roles. Every role is associated with multiple permissions.
A `Role` and a `Permission` are regular Eloquent models. They require a `name` and can be created like this:

```php
use Spatie\Permission\Models\Role;
use Spatie\Permission\Models\Permission;

$role = Role::create(['name' => 'writer']);
$permission = Permission::create(['name' => 'edit articles']);
```

If you're using multiple guards the `guard_name` attribute needs to be set as well. Read about it in the [using multiple guards](#using-multiple-guards) section of the readme.

The `HasRoles` trait adds Eloquent relationships to your models, which can be accessed directly or used as a base query:

```php
// get a list of all permissions directly assigned to the user
$permissions = $user->permissions;

// get all permissions inherited by the user via roles
$permissions = $user->getAllPermissions();

// get a collection of all defined roles
$roles = $user->getRoleNames(); // Returns a collection
```

The `HasRoles` trait also adds a `role` scope to your models to scope the query to certain roles or permissions:

```php
$users = User::role('writer')->get(); // Returns only users with the role 'writer'
```

The `role` scope can accept a string, a `\Spatie\Permission\Models\Role` object or an `\Illuminate\Support\Collection` object.

The same trait also adds a scope to only get users that have a certain permission.

```php
$users = User::permission('edit articles')->get(); // Returns only users with the permission 'edit articles' (inherited or directly)
```

The scope can accept a string, a `\Spatie\Permission\Models\Permission` object or an `\Illuminate\Support\Collection` object.

### Using "direct" permissions (see below to use both roles and permissions)

A permission can be given to any user:

```php
$user->givePermissionTo('edit articles');

// You can also give multiple permission at once
$user->givePermissionTo('edit articles', 'delete articles');

// You may also pass an array
$user->givePermissionTo(['edit articles', 'delete articles']);
```

A permission can be revoked from a user:

```php
$user->revokePermissionTo('edit articles');
```

Or revoke & add new permissions in one go:

```php
$user->syncPermissions(['edit articles', 'delete articles']);
```

You can test if a user has a permission:

```php
$user->hasPermissionTo('edit articles');
```

...or if a user has multiple permissions:

```php
$user->hasAnyPermission(['edit articles', 'publish articles', 'unpublish articles']);
```

Saved permissions will be registered with the `Illuminate\Auth\Access\Gate` class for the default guard. So you can
test if a user has a permission with Laravel's default `can` function:

```php
$user->can('edit articles');
```

### Using permissions via roles

A role can be assigned to any user:

```php
$user->assignRole('writer');

// You can also assign multiple roles at once
$user->assignRole('writer', 'admin');
// or as an array
$user->assignRole(['writer', 'admin']);
```

A role can be removed from a user:

```php
$user->removeRole('writer');
```

Roles can also be synced:

```php
// All current roles will be removed from the user and replaced by the array given
$user->syncRoles(['writer', 'admin']);
```

You can determine if a user has a certain role:

```php
$user->hasRole('writer');
```

You can also determine if a user has any of a given list of roles:

```php
$user->hasAnyRole(Role::all());
```

You can also determine if a user has all of a given list of roles:

```php
$user->hasAllRoles(Role::all());
```

The `assignRole`, `hasRole`, `hasAnyRole`, `hasAllRoles`  and `removeRole` functions can accept a
 string, a `\Spatie\Permission\Models\Role` object or an `\Illuminate\Support\Collection` object.

A permission can be given to a role:

```php
$role->givePermissionTo('edit articles');
```

You can determine if a role has a certain permission:

```php
$role->hasPermissionTo('edit articles');
```

A permission can be revoked from a role:

```php
$role->revokePermissionTo('edit articles');
```

The `givePermissionTo` and `revokePermissionTo` functions can accept a
string or a `Spatie\Permission\Models\Permission` object.


Permissions are inherited from roles automatically. 
Additionally, individual permissions can be assigned to the user too. 
For instance:

```php
$role = Role::findByName('writer');
$role->givePermissionTo('edit articles');

$user->assignRole('writer');

$user->givePermissionTo('delete articles');
```

In the above example, a role is given permission to edit articles and this role is assigned to a user. 
Now the user can edit articles and additionally delete articles. The permission of 'delete articles' is the user's direct permission because it is assigned directly to them.
When we call `$user->hasDirectPermission('delete articles')` it returns `true`, 
but `false` for `$user->hasDirectPermission('edit articles')`.

This method is useful if one builds a form for setting permissions for roles and users in an application and wants to restrict or change inherited permissions of roles of the user, i.e. allowing to change only direct permissions of the user.

You can list all of these permissions:

```php
// Direct permissions
$user->getDirectPermissions() // Or $user->permissions;

// Permissions inherited from the user's roles
$user->getPermissionsViaRoles();

// All permissions which apply on the user (inherited and direct)
$user->getAllPermissions();
```

All these responses are collections of `Spatie\Permission\Models\Permission` objects.

If we follow the previous example, the first response will be a collection with the `delete article` permission and 
the second will be a collection with the `edit article` permission and the third will contain both.

### Using Blade directives
This package also adds Blade directives to verify whether the currently logged in user has all or any of a given list of roles. 

Optionally you can pass in the `guard` that the check will be performed on as a second argument.

#### Blade and Roles
Test for a specific role:
```php
@role('writer')
    I am a writer!
@else
    I am not a writer...
@endrole
```
is the same as
```php
@hasrole('writer')
    I am a writer!
@else
    I am not a writer...
@endhasrole
```

Test for any role in a list:
```php
@hasanyrole($collectionOfRoles)
    I have one or more of these roles!
@else
    I have none of these roles...
@endhasanyrole
// or
@hasanyrole('writer|admin')
    I am either a writer or an admin or both!
@else
    I have none of these roles...
@endhasanyrole
```
Test for all roles:

```php
@hasallroles($collectionOfRoles)
    I have all of these roles!
@else
    I do not have all of these roles...
@endhasallroles
// or
@hasallroles('writer|admin')
    I am both a writer and an admin!
@else
    I do not have all of these roles...
@endhasallroles
```

#### Blade and Permissions
This package doesn't add any permission-specific Blade directives. Instead, use Laravel's native `@can` directive to check if a user has a certain permission.

```php
@can('edit articles')
  //
@endcan
```
or
```php
@if(auth()->user()->can('edit articles') && $some_other_condition)
  //
@endif
```

## Using multiple guards

When using the default Laravel auth configuration all of the above methods will work out of the box, no extra configuration required.

However, when using multiple guards they will act like namespaces for your permissions and roles. Meaning every guard has its own set of permissions and roles that can be assigned to their user model.

### Using permissions and roles with multiple guards

By default the default guard (`config('auth.defaults.guard')`) will be used as the guard for new permissions and roles. When creating permissions and roles for specific guards you'll have to specify their `guard_name` on the model:

```php
// Create a superadmin role for the admin users
$role = Role::create(['guard_name' => 'admin', 'name' => 'superadmin']);

// Define a `publish articles` permission for the admin users belonging to the admin guard
$permission = Permission::create(['guard_name' => 'admin', 'name' => 'publish articles']);

// Define a *different* `publish articles` permission for the regular users belonging to the web guard
$permission = Permission::create(['guard_name' => 'web', 'name' => 'publish articles']);
```

To check if a user has permission for a specific guard:

```php
$user->hasPermissionTo('publish articles', 'admin');
```

### Assigning permissions and roles to guard users

You can use the same methods to assign permissions and roles to users as described above in [using permissions via roles](#using-permissions-via-roles). Just make sure the `guard_name` on the permission or role matches the guard of the user, otherwise a `GuardDoesNotMatch` exception will be thrown.

### Using blade directives with multiple guards

You can use all of the blade directives listed in [using blade directives](#using-blade-directives) by passing in the guard you wish to use as the second argument to the directive:

```php
@role('super-admin', 'admin')
    I am a super-admin!
@else
    I am not a super-admin...
@endrole
```

## Using a middleware

This package comes with `RoleMiddleware` and `PermissionMiddleware` middleware. You can add them inside your `app/Http/Kernel.php` file.

```php
protected $routeMiddleware = [
    // ...
    'role' => \Spatie\Permission\Middlewares\RoleMiddleware::class,
    'permission' => \Spatie\Permission\Middlewares\PermissionMiddleware::class,
];
```

Then you can protect your routes using middleware rules:

```php
Route::group(['middleware' => ['role:super-admin']], function () {
    //
});

Route::group(['middleware' => ['permission:publish articles']], function () {
    //
});

Route::group(['middleware' => ['role:super-admin','permission:publish articles']], function () {
    //
});
```

Alternatively, you can separate multiple roles or permission with a `|` (pipe) character:

```php
Route::group(['middleware' => ['role:super-admin|writer']], function () {
    //
});

Route::group(['middleware' => ['permission:publish articles|edit articles']], function () {
    //
});
```

You can protect your controllers similarly, by setting desired middleware in the constructor:

```php
public function __construct()
{
    $this->middleware(['role:super-admin','permission:publish articles|edit articles']);
}
```

### Catching role and permission failures
If you want to override the default `403` response, you can catch the `UnauthorizedException` using your app's exception handler:

```php
public function render($request, Exception $exception)
{
    if ($exception instanceof \Spatie\Permission\Exceptions\UnauthorizedException) {
        // Code here ...
    }

    return parent::render($request, $exception);
}

```

## Using artisan commands

You can create a role or permission from a console with artisan commands.

```bash
php artisan permission:create-role writer
```

```bash
php artisan permission:create-permission 'edit articles'
```

When creating permissions and roles for specific guards you can specify the guard names as a second argument:

```bash
php artisan permission:create-role writer web
```

```bash
php artisan permission:create-permission 'edit articles' web
```

## Unit Testing

In your application's tests, if you are not seeding roles and permissions as part of your test `setUp()` then you may run into a chicken/egg situation where roles and permissions aren't registered with the gate (because your tests create them after that gate registration is done). Working around this is simple: In your tests simply add a `setUp()` instruction to re-register the permissions, like this:

```php
    public function setUp()
    {
        // first include all the normal setUp operations
        parent::setUp();

        // now re-register all the roles and permissions
        $this->app->make(\Spatie\Permission\PermissionRegistrar::class)->registerPermissions();
    }
```

## Database Seeding

Two notes about Database Seeding:

1. It is best to flush the `spatie.permission.cache` before seeding, to avoid cache conflict errors. This can be done from an Artisan command (see Troubleshooting: Cache section, later) or directly in a seeder class (see example below).

2. Here's a sample seeder, which clears the cache, creates permissions and then assigns permissions to roles:

	```php
	use Illuminate\Database\Seeder;
	use Spatie\Permission\Models\Role;
	use Spatie\Permission\Models\Permission;

	class RolesAndPermissionsSeeder extends Seeder
	{
	    public function run()
    	{
        	// Reset cached roles and permissions
	        app()['cache']->forget('spatie.permission.cache');

	        // create permissions
	        Permission::create(['name' => 'edit articles']);
	        Permission::create(['name' => 'delete articles']);
	        Permission::create(['name' => 'publish articles']);
	        Permission::create(['name' => 'unpublish articles']);

	        // create roles and assign existing permissions
	        $role = Role::create(['name' => 'writer']);
	        $role->givePermissionTo('edit articles');
	        $role->givePermissionTo('delete articles');

	        $role = Role::create(['name' => 'admin']);
	        $role->givePermissionTo('publish articles');
	        $role->givePermissionTo('unpublish articles');
	    }
	}

	```

## Extending

If you need to extend or replace the existing `Role` or `Permission` models you just need to
keep the following things in mind:

- Your `Role` model needs to implement the `Spatie\Permission\Contracts\Role` contract
- Your `Permission` model needs to implement the `Spatie\Permission\Contracts\Permission` contract
- You can publish the configuration with this command:

```bash
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider" --tag="config"
```
  
  And update the `models.role` and `models.permission` values


## Cache

Role and Permission data are cached to speed up performance.

When you use the supplied methods for manipulating roles and permissions, the cache is automatically reset for you:

```php
$user->assignRole('writer');
$user->removeRole('writer');
$user->syncRoles(params);
$role->givePermissionTo('edit articles');
$role->revokePermissionTo('edit articles');
$role->syncPermissions(params);
```

HOWEVER, if you manipulate permission/role data directly in the database instead of calling the supplied methods, then you will not see the changes reflected in the application unless you manually reset the cache.

### Manual cache reset
To manually reset the cache for this package, run:
```bash
php artisan cache:forget spatie.permission.cache
```

### Cache Identifier

TIP: If you are leveraging a caching service such as `redis` or `memcached` and there are other sites 
running on your server, you could run into cache clashes. It is prudent to set your own cache `prefix` 
in `/config/cache.php` to something unique for each application. This will prevent other applications 
from accidentally using/changing your cached data.

## UI Resources

The package doesn't come with any screens out of the box, you should build that yourself.

- [How to create a UI for managing the permissions and roles](http://www.qcode.in/easy-roles-and-permissions-in-laravel-5-4/)
- [User Authorization in Laravel 5.4 with Spatie Laravel-Permission](https://scotch.io/tutorials/user-authorization-in-laravel-54-with-spatie-laravel-permission) by [Caleb Oki](http://www.caleboki.com/).

## Testing

``` bash
composer test
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

### Security

If you discover any security-related issues, please email [freek@spatie.be](mailto:freek@spatie.be) instead of using the issue tracker.

## Postcardware

You're free to use this package, but if it makes it to your production environment we highly appreciate you sending us a postcard from your hometown, mentioning which of our package(s) you are using.

Our address is: Spatie, Samberstraat 69D, 2060 Antwerp, Belgium.

We publish all received postcards [on our company website](https://spatie.be/en/opensource/postcards).

## Credits

- [Freek Van der Herten](https://github.com/freekmurze)
- [All Contributors](../../contributors)

This package is heavily based on [Jeffrey Way](https://twitter.com/jeffrey_way)'s awesome [Laracasts](https://laracasts.com) lessons
on [permissions and roles](https://laracasts.com/series/whats-new-in-laravel-5-1/episodes/16). His original code
can be found [in this repo on GitHub](https://github.com/laracasts/laravel-5-roles-and-permissions-demo).

Special thanks to [Alex Vanderbist](https://github.com/AlexVanderbist) who greatly helped with `v2`, and to [Chris Brown](https://github.com/drbyte) for his longtime support  helping us maintain the package.

## Alternatives

[Povilas Korop](https://twitter.com/@povilaskorop) did an excellent job listing the alternatives [in an article on Laravel News](https://laravel-news.com/two-best-roles-permissions-packages). In that same article, he compares laravel-permission to [Joseph Silber](https://github.com/JosephSilber)'s [Bouncer]((https://github.com/JosephSilber/bouncer)), which in our book is also an excellent package.

## Sponsor

<img style="width:90px; height:30px; vertical-align:middle;" 
    src="data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiIHN0YW5kYWxvbmU9Im5vIj8+Cjxzdmcgd2lkdGg9IjQ2MnB4IiBoZWlnaHQ9IjE2OHB4IiB2aWV3Qm94PSIwIDAgNDYyIDE2OCIgdmVyc2lvbj0iMS4xIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB4bWxuczpza2V0Y2g9Imh0dHA6Ly93d3cuYm9oZW1pYW5jb2RpbmcuY29tL3NrZXRjaC9ucyI+CiAgICA8IS0tIEdlbmVyYXRvcjogU2tldGNoIDMuMC4zICg3ODkxKSAtIGh0dHA6Ly93d3cuYm9oZW1pYW5jb2RpbmcuY29tL3NrZXRjaCAtLT4KICAgIDx0aXRsZT5VbnRpdGxlZDwvdGl0bGU+CiAgICA8ZGVzYz5DcmVhdGVkIHdpdGggU2tldGNoLjwvZGVzYz4KICAgIDxkZWZzPjwvZGVmcz4KICAgIDxnIGlkPSJQYWdlLTEiIHN0cm9rZT0ibm9uZSIgc3Ryb2tlLXdpZHRoPSIxIiBmaWxsPSJub25lIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiIHNrZXRjaDp0eXBlPSJNU1BhZ2UiPgogICAgICAgIDxnIGlkPSJsb2dvLWJsdWUtaG9yaXpvbnRhbCIgc2tldGNoOnR5cGU9Ik1TTGF5ZXJHcm91cCI+CiAgICAgICAgICAgIDxnIGlkPSJHcm91cCIgc2tldGNoOnR5cGU9Ik1TU2hhcGVHcm91cCI+CiAgICAgICAgICAgICAgICA8ZyBpZD0iQ2xpcHBlZCIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTg4LjAwMDAwMCwgNDQuMDAwMDAwKSIgZmlsbD0iIzE2MjE0RCI+CiAgICAgICAgICAgICAgICAgICAgPHBhdGggZD0iTTI0Ni41MTcsMC4xMSBDMjM4LjQzOSwwLjExIDIzMS42MDcsMy45MTYgMjI2Ljc1OSwxMS4xMTUgQzIyMS45NCwxOC4yNzEgMjE5LjM5MywyOC4yNiAyMTkuMzkzLDQwIEMyMTkuMzkzLDUxLjc0IDIyMS45NCw2MS43MjkgMjI2Ljc1OSw2OC44ODQgQzIzMS42MDcsNzYuMDg0IDIzOC40MzksNzkuODg5IDI0Ni41MTcsNzkuODg5IEMyNTQuNTk1LDc5Ljg4OSAyNjEuNDI3LDc2LjA4NCAyNjYuMjc1LDY4Ljg4NCBDMjcxLjA5Myw2MS43MjkgMjczLjY0LDUxLjc0IDI3My42NCw0MCBDMjczLjY0LDI4LjI2IDI3MS4wOTMsMTguMjcxIDI2Ni4yNzUsMTEuMTE1IEMyNjEuNDI3LDMuOTE2IDI1NC41OTUsMC4xMSAyNDYuNTE3LDAuMTEgTDI0Ni41MTcsMC4xMSBaIE0yNDYuNTE3LDcwLjAwNSBDMjQyLjY1NSw3MC4wMDUgMjM5LjYwNCw2Ny44MiAyMzcuMTg3LDYzLjMyNCBDMjM0LjI2OCw1Ny44OTMgMjMyLjY2LDQ5LjYxIDIzMi42Niw0MCBDMjMyLjY2LDMwLjM5IDIzNC4yNjgsMjIuMTA2IDIzNy4xODcsMTYuNjc2IEMyMzkuNjA0LDEyLjE4IDI0Mi42NTUsOS45OTQgMjQ2LjUxNyw5Ljk5NCBDMjUwLjM3OCw5Ljk5NCAyNTMuNDMsMTIuMTggMjU1Ljg0NywxNi42NzYgQzI1OC43NjYsMjIuMTA2IDI2MC4zNzMsMzAuMzg5IDI2MC4zNzMsNDAgQzI2MC4zNzMsNDkuNjExIDI1OC43NjYsNTcuODk1IDI1NS44NDcsNjMuMzI0IEMyNTMuNDMsNjcuODIgMjUwLjM3OCw3MC4wMDUgMjQ2LjUxNyw3MC4wMDUgTDI0Ni41MTcsNzAuMDA1IFogTTcxLjQ1LDI5LjE3MiBMNzEuNDUsNjMuNDg0IEM3MS40NSw3Mi41MyA3OC44MSw3OS44ODkgODcuODU2LDc5Ljg4OSBDOTUuNzQ2LDc5Ljg4OSAxMDEuNzA3LDc1Ljk3NSAxMDMuOTAyLDc0LjI5MSBDMTA0LjAyNCw3NC4xOTcgMTA0LjE4NCw3NC4xNjkgMTA0LjMzMSw3NC4yMTYgQzEwNC40NzgsNzQuMjYzIDEwNC41OTIsNzQuMzc5IDEwNC42MzcsNzQuNTI3IEwxMDUuOTYxLDc4Ljg2IEwxMTUuNzM3LDc4Ljg2IEwxMTUuNzM3LDI5LjE3MiBMMTAzLjE3NSwyOS4xNzIgTDEwMy4xNzUsNjYuMzI2IEMxMDMuMTc1LDY2LjUwMSAxMDMuMDc2LDY2LjY2MiAxMDIuOTIxLDY2Ljc0MyBDMTAwLjU1OSw2Ny45NjEgOTUuODk5LDcwLjAwNiA5MS4yMzEsNzAuMDA2IEM4Ny4yNTIsNzAuMDA2IDg0LjAxMiw2Ni43NjggODQuMDEyLDYyLjc4NyBMODQuMDEyLDI5LjE3MiBMNzEuNDUsMjkuMTcyIEw3MS40NSwyOS4xNzIgWiBNMTk3LjIzNyw3OC44NTkgTDIwOS44LDc4Ljg1OSBMMjA5LjgsNDQuNTQ3IEMyMDkuOCwzNS41MDEgMjAyLjQ0LDI4LjE0MSAxOTMuMzk0LDI4LjE0MSBDMTg2LjczNSwyOC4xNDEgMTgxLjM5MywzMS4wMDQgMTc4LjgwMiwzMi43MSBDMTc4LjY1NywzMi44MDUgMTc4LjQ3MywzMi44MTMgMTc4LjMyMiwzMi43MzEgQzE3OC4xNzEsMzIuNjQ5IDE3OC4wNzUsMzIuNDkxIDE3OC4wNzUsMzIuMzE4IEwxNzguMDc1LDEuMTQxIEwxNjUuNTEzLDEuMTQxIEwxNjUuNTEzLDc4Ljg1OSBMMTc4LjA3NSw3OC44NTkgTDE3OC4wNzUsNDEuNzA0IEMxNzguMDc1LDQxLjUyOSAxNzguMTc0LDQxLjM2OCAxNzguMzMsNDEuMjg4IEMxODAuNjkxLDQwLjA2OSAxODUuMzUyLDM4LjAyNSAxOTAuMDE5LDM4LjAyNSBDMTkxLjk0NywzOC4wMjUgMTkzLjc2LDM4Ljc3NiAxOTUuMTIzLDQwLjEzOSBDMTk2LjQ4Niw0MS41MDIgMTk3LjIzNiw0My4zMTYgMTk3LjIzNiw0NS4yNDMgTDE5Ny4yMzYsNzguODU5IEwxOTcuMjM3LDc4Ljg1OSBaIE0xMjQuNzkyLDM5LjA1NSBMMTMyLjQzOCwzOS4wNTUgQzEzMi42OTcsMzkuMDU1IDEzMi45MDcsMzkuMjY1IDEzMi45MDcsMzkuNTI0IEwxMzIuOTA3LDY2Ljg1OCBDMTMyLjkwNyw3NC4wNDMgMTM4Ljc1Myw3OS44ODggMTQ1LjkzOCw3OS44ODggQzE0OC41NDMsNzkuODg4IDE1MS4xMTMsNzkuNTEyIDE1My41ODUsNzguNzcgTDE1My41ODUsNjkuNzk2IEMxNTIuMTQzLDY5LjkyMyAxNTAuNDg1LDcwLjAwNSAxNDkuMzEzLDcwLjAwNSBDMTQ3LjE5Myw3MC4wMDUgMTQ1LjQ2OSw2OC4yOCAxNDUuNDY5LDY2LjE2MSBMMTQ1LjQ2OSwzOS41MjMgQzE0NS40NjksMzkuMjY0IDE0NS42NzksMzkuMDU0IDE0NS45MzgsMzkuMDU0IEwxNTMuNTg1LDM5LjA1NCBMMTUzLjU4NSwyOS4xNzEgTDE0NS45MzgsMjkuMTcxIEMxNDUuNjc5LDI5LjE3MSAxNDUuNDY5LDI4Ljk2MSAxNDUuNDY5LDI4LjcwMiBMMTQ1LjQ2OSwxMi4yOTUgTDEzMi45MDcsMTIuMjk1IEwxMzIuOTA3LDI4LjcwMiBDMTMyLjkwNywyOC45NjEgMTMyLjY5NywyOS4xNzEgMTMyLjQzOCwyOS4xNzEgTDEyNC43OTIsMjkuMTcxIEwxMjQuNzkyLDM5LjA1NSBMMTI0Ljc5MiwzOS4wNTUgWiBNNTEuMzYxLDc4Ljg1OSBMNjQuNDI5LDc4Ljg1OSBMNDQuNTU1LDkuNTUgQzQyLjk2MiwzLjk5MiAzNy44MTEsMC4xMSAzMi4wMjksMC4xMSBDMjYuMjQ3LDAuMTEgMjEuMDk2LDMuOTkyIDE5LjUwMiw5LjU1IEwtMC4zNzIsNzguODU5IEwxMi42OTcsNzguODU5IEwxOC40NDksNTguNzk4IEMxOC41MDcsNTguNTk3IDE4LjY5MSw1OC40NTkgMTguOSw1OC40NTkgTDQ1LjE1OCw1OC40NTkgQzQ1LjM2Nyw1OC40NTkgNDUuNTUyLDU4LjU5NyA0NS42MDksNTguNzk4IEw1MS4zNjEsNzguODU5IEw1MS4zNjEsNzguODU5IFogTTQyLjA1Niw0OC41NzYgTDIyLjAwNCw0OC41NzYgQzIxLjg1Nyw0OC41NzYgMjEuNzE4LDQ4LjUwNyAyMS42MjksNDguMzg4IEMyMS41NDEsNDguMjcyIDIxLjUxMyw0OC4xMTkgMjEuNTUzLDQ3Ljk3OCBMMzEuNTc5LDEzLjAxMiBDMzEuNjM3LDEyLjgxMSAzMS44MjEsMTIuNjczIDMyLjAzLDEyLjY3MyBDMzIuMjM5LDEyLjY3MyAzMi40MjMsMTIuODExIDMyLjQ4LDEzLjAxMiBMNDIuNTA3LDQ3Ljk3OCBDNDIuNTQ3LDQ4LjEyIDQyLjUxOSw0OC4yNzIgNDIuNDMsNDguMzg4IEM0Mi4zNDIsNDguNTA3IDQyLjIwMyw0OC41NzYgNDIuMDU2LDQ4LjU3NiBMNDIuMDU2LDQ4LjU3NiBaIiBpZD0iU2hhcGUiPjwvcGF0aD4KICAgICAgICAgICAgICAgIDwvZz4KICAgICAgICAgICAgICAgIDxnIGlkPSJDbGlwcGVkIiBmaWxsPSIjRUI1NDI0Ij4KICAgICAgICAgICAgICAgICAgICA8cGF0aCBkPSJNMTE5LjU1NSwxMzUuODYxIEwxMDIuNzA1LDgzLjk5NyBMMTQ2LjgxMyw1MS45NTIgTDkyLjI5MSw1MS45NTIgTDc1LjQ0LDAuMDkgTDc1LjQzNSwwLjA3NiBMMTI5Ljk2NSwwLjA3NiBMMTQ2LjgyLDUxLjk0NyBMMTQ2LjgyMSw1MS45NDYgTDE0Ni44MzUsNTEuOTM4IEMxNTYuNjIzLDgyLjAzIDE0Ni41NDIsMTE2LjI1NiAxMTkuNTU1LDEzNS44NjEgTDExOS41NTUsMTM1Ljg2MSBaIE0zMS4zMjEsMTM1Ljg2MSBMMzEuMzA3LDEzNS44NzEgTDc1LjQyNiwxNjcuOTI0IEwxMTkuNTU1LDEzNS44NjIgTDc1LjQ0LDEwMy44MDggTDMxLjMyMSwxMzUuODYxIEwzMS4zMjEsMTM1Ljg2MSBaIE00LjA1Miw1MS45MzkgTDQuMDUyLDUxLjkzOSBDLTYuMjUyLDgzLjY2IDUuNzA5LDExNy4yNzIgMzEuMzEyLDEzNS44NjcgTDMxLjMxNiwxMzUuODUxIEw0OC4xNjgsODMuOTkgTDQuMDcsNTEuOTUxIEw1OC41NzksNTEuOTUxIEw3NS40MzEsMC4wODkgTDc1LjQzNSwwLjA3NSBMMjAuOTAyLDAuMDc1IEw0LjA1Miw1MS45MzkgTDQuMDUyLDUxLjkzOSBaIiBpZD0iU2hhcGUiPjwvcGF0aD4KICAgICAgICAgICAgICAgIDwvZz4KICAgICAgICAgICAgPC9nPgogICAgICAgIDwvZz4KICAgIDwvZz4KPC9zdmc+">

This package is kindly sponsored by [Auth0](https://auth0.com) – The new way to solve Identity.

Auth0 solves the most complex and large-scale identity use cases for global enterprises with their extensible and easy-to-integrate platform, securing billions of logins every year.

## Support us

Spatie is a web design agency based in Antwerp, Belgium. You'll find an overview of all our open source projects [on our website](https://spatie.be/opensource).

Does your business depend on our contributions? Reach out and support us on [Patreon](https://www.patreon.com/spatie). 
All pledges will be dedicated to allocating workforce on maintenance and new awesome stuff.

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
