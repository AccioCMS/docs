# Factories

## Introduction
çka jane pse jane.

Read [Laravel Documentation ](https://laravel.com/docs/5.7/database-testing) for more details

Na kena factories per
@todo, keto me i lidh me dokumentim te kodit (sami)

- Category
- CustomField
- Language
- Media
- Menu
- MenuLink
- Post
- Post Type
- Tag
- User

## Using Factories
Once you have defined your factories, you may use the global factory function in your tests or seed files to generate model instances.
So, let's take a look at an example of creating model. First, we'll use the make method to create models but not save them to the database:

```php
public function testDatabase()
{
    $user = factory(App\User::class)->make();

    // Use model in tests...
}
````
By using `create` method you not only create the model instances but also save them to the database using Eloquent's save method:

```php
public function testDatabase()
{
    // Create a single App\User instance...
    $user = factory(App\User::class)->create();

    // Create three App\User instances...
    $users = factory(App\User::class, 3)->create();

    // Use model in tests...
}
````
You may override attributes on the model by passing an array to the create method:

```php
$user = factory(App\User::class)->create([
    'name' => 'Abigail',
]);
````


