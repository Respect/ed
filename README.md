# Respected

Dependency containers for components from the PHP Comunity to be used by
[Respect\Config](http://github.com/Respect/Config).

# Introduction

PHP has lots of frameworks and thousands of great components, would't be great
if there was a way to use the components in a very simple and direct manner?

Respected aims to be a repository to do just that! Holding the dependency management
for great components out there, so we can easily use them and personalize their configuration
as you see fit.

PS: all the declared components are __lazy-loaded__, things are only insantiated
when they are really need.

# What components do you cover

Look for all the INIs in this repository, each one is a different component, ready 
to use. See the examples below for little more information.

PS: before using the components, be sure they are already available to the application.

## Doctrine 2

Before using it you should change database configuration and add entity paths
related to your project in the INI.

```php
<?php
use Respect\Config\Container;
use My\Application\Entity\User; // Example entity

$doctrine = new Container('Doctrine.ini'); // Should point to your ini path
$user     = new User('Respect');
$doctrine->entityManager->persist($user);
$doctrine->entityManager->flush();
?>
```

## Twig

Before using this Twig you should change the location where your templates are
in the INI.

```php
<?php
use Respect\Config\Container;

$doctrine = new Container('Twig.ini'); // Should point to your ini path
$doctrine->twig->render('index.html', array('name'=>'Respect'));
?>
```

# Instalation

This repository serves as a very quick way of declaring dependencies
for projects outside Respect that are complient with the PSR#0. This is not meant 
to be installed.

Somwhere in the future we (or you, who knows?!) have the intention to serve it
in a better way, by now: copy and paste the INI that references the component
you want to use inside your project, change some variables (if needed) and
instantiate it with [Respect\Config](http://github.com/Respect/Config).

# How do I make my own INI?

For documentation on this, you should refer to [Respect\Config](http://github.com/Respect/Config).