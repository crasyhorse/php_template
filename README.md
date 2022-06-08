# PHP template repository

## Description

This repository works as a template for new PHP projects. It contains
* a ```.gitignore``` file with the following entries:
```
/vendor
.phpunit.result.cache
.editorconfig
/reports
.scannerwork/**
junit.xml
/docs/cache
.php-cs-fixer.cache
*.code-workspace
```
* fully fletched PHP-Cs-Fixer configuration in ```.php_cs.php``` file using PSR-12 standard
* a BSD-3 license
* a PHP-Documentor configuration using ```onspli/phpdoc-markdown``` markdown-template (Replace text in ```<title>``` tags).
* a configuration for PHP-Unit 9.5 
  * with two test suites configured ("Unit" and "Integration"), looking for tests in ```/tests```
  * and code coverage with html output enabled
* a configuration file for Psalm

The following packages are defined in the ```composer.json``` file
```json
"require": {
        "php": "^7.4 | ^8.0",
        "ext-json": "*",
        "adbario/php-dot-notation": "2.x-dev",
        "nesbot/carbon": "^2.58.0",
        "opis/json-schema": "^2.3.0",
        "marc-mabe/php-enum": "^4.7.0",
        "onspli/phpdoc-markdown": "dev-master",
        "squizlabs/php_codesniffer": "*"
    },
    "require-dev": {
        "phpunit/phpunit": "^9.5",
        "vimeo/psalm": "^4.23.0",
        "friendsofphp/php-cs-fixer": "^3.8.0"
    }
```

Additionally there are these Composer scripts predefined:
```json
"scripts": {
        "phpcs": "vendor/bin/phpcs --standard=PSR12 src",
        "phpdoc": "vendor/bin/phpDocumentor.phar",
        "psalm": "vendor/bin/psalm",
        "psalm-c": "vendor/bin/psalm --clear-cache",
        "psalm-i": "vendor/bin/psalm --show-info=true",
        "test:integration": "vendor/bin/phpunit --testsuite Integration --no-coverage --color=always",
        "test:unit": "vendor/bin/phpunit --testsuite Unit --color=always || true",
        "test:unit-f": "vendor/bin/phpunit --testsuite Unit --filter"
    }
```

## Usage

To use this template look for the string "TEMPLATE" in ```composer.json``` and ```phpdoc.dist.xml```. Please replace all occurences with useful values. 

Although a PHP-Documentor configuration is included in this template, PHP-Documentor itself is not. It is recommended to install PHP-Documentor globally by using ```phpDocumentor.phar``` file.