ISDev Twitter Bootstrap Bundle (lessphp branch)
===============================================

Warning
-------

The current version of [lessphp](http://leafo.net/lessphp/) (0.3.3) does not support all of the syntax used in twitter bootstrap less files.

Description
-----------

Simple and easy to install [Symfony 2](http://symfony.com/) bundle for the implementation of [Twitter Bootstrap](http://twitter.github.com/bootstrap/).

Installation
------------

1. Include repository in your `deps` file:

    ``` ini
    [lessphp]
        git=git://github.com/leafo/lessphp.git
        target=/lessphp
        version=v0.3.3

    [twitter-bootstrap]
        git=git://github.com/twitter/bootstrap.git
        target=/twitter/bootstrap
        version=v2.0.2

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

4. Register assetic filter to compile [LESS](http://lesscss.org/) in the CSS in `app/config/config.yml` file:

    ``` ini
    assetic:
        # ...
        filters:
            # ...
            lessphp:
                file: %kernel.root_dir%/../vendor/lessphp/lessc.inc.php
                apply_to: "\.less$"
    ```

5. Register twig form template for whole project in `app/config/config.yml` file:

    ``` yaml
    twig:
        # ...
        form:
            resources:
                - 'IsdevTwitterBootstrapBundle:Form:fields.html.twig'
    ```

    Or include the `fields.html.twig` in your template for a special form:

    ``` jinja
    {% form_theme special_form 'IsdevTwitterBootstrapBundle:Form:fields.html.twig' %}
    ```

6. Bundle includes the basic template. For a quick start you can just inherit from it your template:

    ``` jinja
    {% extends "IsdevTwitterBootstrapBundle::base.html.twig" %}
    ```

TO-DO list
----------

- refine form template
- fix lessphp