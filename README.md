PHPCSDevCS for developers of PHP_CodeSniffer sniffs
=====================================================

[![Latest Stable Version](https://poser.pugx.org/phpcsstandards/phpcsdevcs/v/stable)](https://packagist.org/packages/phpcsstandards/phpcsdevcs)
[![Release Date of the Latest Version](https://img.shields.io/github/release-date/PHPCSStandards/PHPCSDevCS.svg?maxAge=1800)](https://github.com/PHPCSStandards/PHPCSDevCS/releases)
:construction:
[![Latest Unstable Version](https://img.shields.io/badge/unstable-dev--main-e68718.svg?maxAge=2419200)](https://packagist.org/packages/phpcsstandards/phpcsdevcs#dev-main)
[![Build Status](https://github.com/PHPCSStandards/PHPCSDevCS/workflows/CI/badge.svg?branch=main)](https://github.com/PHPCSStandards/PHPCSDevCS/actions)
[![Last Commit to Unstable](https://img.shields.io/github/last-commit/PHPCSStandards/PHPCSDevCS/main.svg)](https://github.com/PHPCSStandards/PHPCSDevCS/commits/main)

[![Minimum PHP Version](https://img.shields.io/packagist/php-v/phpcsstandards/phpcsdevcs.svg?maxAge=3600)](https://packagist.org/packages/phpcsstandards/phpcsdevcs)
[![License: LGPLv3](https://poser.pugx.org/phpcsstandards/phpcsdevcs/license)](https://github.com/PHPCSStandards/PHPCSDevCS/blob/main/LICENSE)
![Awesome](https://img.shields.io/badge/awesome%3F-yes!-brightgreen.svg)


This is an external ruleset for [PHP CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) intended for use by sniff developers.

* [Installation](#installation)
    + [Composer Project-based Installation](#composer-project-based-installation)
    + [Composer Global Installation](#composer-global-installation)
* [PHPCSDev ruleset for sniff repos](#phpcsdev-ruleset-for-sniff-repos)
    + [Using the ruleset from the command line](#using-the-ruleset-from-the-command-line)
    + [Using the ruleset from within a project based ruleset](#using-the-ruleset-from-within-a-project-based-ruleset)
* [Contributing](#contributing)
* [License](#license)


Installation
-------------------------------------------

### Composer Project-based Installation

Run the following from the root of your project:
```bash
composer config allow-plugins.dealerdirect/phpcodesniffer-composer-installer true
composer require --dev phpcsstandards/phpcsdevcs:"^1.0"
```

### Composer Global Installation

If you work on several different sniff repos, you may want to install this toolset globally:
```bash
composer global config allow-plugins.dealerdirect/phpcodesniffer-composer-installer true
composer global require --dev phpcsstandards/phpcsdevcs:"^1.0"
```

Composer will automatically install dependencies and register the PHPCSDev and other external standards with PHP_CodeSniffer using the [Composer PHPCS plugin](https://github.com/PHPCSStandards/composer-installer).


PHPCSDev ruleset for sniff repos
------------------------------

Once this project is installed, you will see a new `PHPCSDev` ruleset in the list of installed standards when you run `phpcs -i`.

**Important: This ruleset currently requires PHP_CodeSniffer >= `3.5.0+`.**

> As sniffs developers will mostly work with the latest version of PHP_CodeSniffer, this shouldn't cause any problems.
>
> Similarly, the CS check in automated CI runs should normally be run on a high PHPCS version for the best results.

The `PHPCSDev` standard can be used by sniff developers to check the code style of their sniff repo code.

Often, sniff repos will use the code style of the standard they are adding. However, not all sniff repos are actually about code style.

So for those repos which need a basic standard which will still keep their code-base consistent, this standard should be useful.

The standard checks your code against the following:
* Compliance with [PSR-12](https://www.php-fig.org/psr/psr-12/), with a few exceptions.
* Use of camelCase variable and function names.
* Use of normalized arrays.
* All files, classes, functions and properties are documented with a docblock and contain the minimally needed information.
* A number of arbitrary additional code style and QA checks.
* PHP cross-version compatibility, while allowing for the tokens back-filled by PHPCS itself.
    Note: for optimal results, the project custom ruleset should set the `testVersion` config variable.
    This is not done by default as config variables are currently [difficult](https://github.com/squizlabs/PHP_CodeSniffer/issues/2197) [to overrule](https://github.com/squizlabs/PHP_CodeSniffer/issues/1821).

The ruleset can be used like any other ruleset and specific sniffs and settings can be added to or overruled from a custom project based ruleset.

### Using the ruleset from the command line
```bash
phpcs . --standard=PHPCSDev
```

### Using the ruleset from within a project based ruleset

Add the following line to your project's `phpcs.xml.dist` file:
```xml
<rule ref="PHPCSDev"/>
```


Contributing
-------
Contributions to this project are welcome. Just clone the repo, branch off from `main`, make your changes, commit them and send in a pull request.

If unsure whether the changes you are proposing would be welcome, open an issue first to discuss your proposal.

License
-------
This code is released under the GNU Lesser General Public License (LGPLv3). For more information, visit http://www.gnu.org/copyleft/lesser.html
