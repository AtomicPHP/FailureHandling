FailureHandling
===============
An error and exception handling library for PHP 5.3+

[![Build Status](https://travis-ci.org/niels-nijens/FailureHandling.png?branch=master)](https://travis-ci.org/niels-nijens/FailureHandling)
[![Coverage Status](https://coveralls.io/repos/niels-nijens/FailureHandling/badge.png?branch=master)](https://coveralls.io/r/niels-nijens/FailureHandling?branch=master)
[![Latest Stable Version](https://poser.pugx.org/niels-nijens/failurehandling/v/stable.png)](https://packagist.org/packages/niels-nijens/failurehandling)

## Installation using Composer ##
Add the following to your composer.json:

```
{
    "require": {
        "niels-nijens/failurehandling": "~2.0"
    }
}
```

This library also requires a [PSR-3](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-3-logger-interface.md) compatible logger like [niels-nijens/Logging](https://github.com/niels-nijens/Logging) or [Monolog](https://github.com/Seldaek/monolog) for the actual logging of errors and exceptions.

## Usage ##
To activate handling of errors and exceptions, see the following example code.
```php
use Nijens\FailureHandling\FailureCatcher;
use Nijens\FailureHandling\Handlers\DefaultFailureHandler;
use Nijens\Logging\Logger; // Not included in this library

$logger = new Logger(); // Not included in this library

$failureHandler = new DefaultFailureHandler();
$failureHandler->setLogger($logger);

FailureCatcher::start($failureHandler);
```
