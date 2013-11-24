Allows you to use [Neo4j](http://www.neo4j.org) with [Laravel4](http://www.laravel.com)

Installation
============

Add `niterain\Neo4jPhpOgm` as a requirement to composer.json:

```javascript
{
    "require": {
        "niterain/neo4j-php-ogm": "dev-master"
    }
}
```

Update your packages with `composer update` or install with `composer install`.

Once Composer has installed or updated your packages you need to register Neo4jPhpOgm with Laravel. Open up app/config/app.php and find the providers key towards the bottom and add:

```php
'Niterain\Neo4jPhpOgm\Neo4jPhpOgmServiceProvider',
```

Configuration
=============

Since I like having my config files in one directory, this library checks to see if the settings are in the database.php file in the app/config directory as one of the connections under the 'neo4j' key, but if there isn't one defined, it looks in its local config.php file.

Usage
=====

You add your entities in an Entity folder, from there everything feels much like Doctrine2.

```php
$em = App::make('entityManager');
$user = $em->getRepository('Entity\\User');
$user->add(array('firstName' => 'levi', 'lastName' => 'stanley'));
$em->persist($user);
$em->flush();
```
