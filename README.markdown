ISDev Twitter Bootstrap Bundle
==============================

Description
-----------

Simple and easy to install [Symfony 2](http://symfony.com/) bundle for the implementation of [Twitter Bootstrap](http://twitter.github.com/bootstrap/).

Installation
------------

1. Include repository in your `deps` file:

``` ini
[TwitterBootstrapBundle]
    git=git://github.com/isdev/Twitter-Bootstrap-bundle.git
    target=/bundles/Isdev/TwitterBootstrapBundle
```

2. Add namespace to your `app/autoload.php` file:

``` php
<?php
// ...
$loader->registerNamespaces(array(
    // ...
    'Isdev' => __DIR__.'/../vendor/bundles',
));
```

3. Register bundle in `app/AppKernel.php` file:

``` php
<?php
// ...
public function registerBundles()
{
    $bundles = array(
        // ...
        new Isdev\TwitterBootstrapBundle\IsdevTwitterBootstrapBundle()
    );
    // ...
    return $bundles;
}
```

TO-DO list
----------

- check asseter less filter in php
- form template