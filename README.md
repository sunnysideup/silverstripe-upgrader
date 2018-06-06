# Upgrader

[![Build Status](https://travis-ci.org/silverstripe/silverstripe-upgrader.svg?branch=master)](https://travis-ci.org/silverstripe/silverstripe-upgrader)

Upgrader is a framework for automating the upgrade of code to handle API changes in dependent libraries.

Still under heavy development, in the first case it will provide a PoC of tooling to assist with SilverStriep 3 to 4 upgrades.

Developed by @sminnee and @tractorcow with inspiration and encouragement from @camspiers

## Install

To install globally run:

`composer global require silverstripe/upgrader`

Make sure your `$HOME/.composer/vendor/bin` directory is in your PATH (or the equivalent for your OS e.g. `C:\Users\<COMPUTER NAME>\AppData\Roaming\Composer\vendor\bin` on Windows).

`echo 'export PATH=$PATH:~/.composer/vendor/bin/'  >> ~/.bash_profile`

Then you can run this script with `upgrade-code <command>` in your project root. If not running in the root,
use --root-dir=/path.

### Symphony packages install issues

Usually the requirements for symfony packages are loose enough to allow ^3 or ^4. In my SS 4.2. installation I see that the silverstripe/serve module (for behat testing) requires ^3.

You can run `composer why symfony/process` to see what requires it?

Often you can explicitly require a newer version of Symfony packages then re-run your install command for packages like the upgrader, e.g. `composer require symfony/process ^4 && composer require-dev silverstripe/upgrader`

## Available commands

The following commands are available:
* [`add-namespace`](docs/en/add-namespace.md)
* [`recompose`](docs/en/recompose.md)
* [`doctor`](docs/en/doctor.md)
* [`environment`](docs/en/environment.md)
* [`inspect`](docs/en/inspect.md)
* [`reorganise`](docs/en/reorganise.md)
* [`upgrade`](docs/en/upgrade.md)
* [`webroot`](docs/en/webroot.md)
