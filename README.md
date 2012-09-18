# Respected
 
Dependency containers for components from the PHP Community and managed by
[Respect\Config](http://github.com/Respect/Config) for your convenience.

# Introduction

PHP has loads of frameworks and thousands of great components, would't it be novel
if there was a way to use the components easily and without a fuss?

Respect/Respected is a repository that aims to do just that! Maintaining the dependencies
of all the great components out there, so we can easily use them and personalise their 
configurations to fit our needs.

PS: all the declared components are __lazy-loaded__, things are only instantiated
when they are really needed and otherwise will stay out of your way.

# What components do we cover

Look for all the INIs in this repository, each one is a different component, ready 
to use. See the examples below for more information.

PPS: before using the components, make sure that they are already available to the application.

## Doctrine 2

Before you can use it you must first change database configurations and add entity paths
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

Before using Twig you should configure the location where your templates are
in the INI.

```php
<?php
use Respect\Config\Container;

$template = new Container('Twig.ini'); // Should point to your ini path
$template->twig->render('index.html', array('name'=>'Respect'));
?>
```

# Installation

This repository serves as a very quick way of declaring dependencies
for projects outside Respect that are compliant with the PSR-0 specification. 
It is not meant to be installed.

Sometime in the near future we (or you even, who knows?!) have plans to serve it
in a more structured way but for now: copy and paste the INI that references the 
component you want to use inside your project, change some variables (if needed) and
instantiate it with [Respect\Config](http://github.com/Respect/Config).

# How do I make my own INI?

For documentation on how to write an INI, as well as information about all the other 
awesome and powerful things you can do, please refer to [Respect\Config](http://github.com/Respect/Config).
